# Crime Master - Crime Report Controllers

## Description

This project provides controllers for managing crime reports within a MERN (MongoDB, Express, React, Node.js) based web application. The controllers handle creating, retrieving, assigning officers to, and updating the status of crime reports. It supports file uploads for evidence and utilizes a model to interact with a MongoDB database.

## How to Use

The controllers are designed to be used within an Express.js backend. They handle incoming requests, interact with the `CrimeReport` model, and send responses.

**Prerequisites:**

*   Node.js and npm/yarn installed.
*   MongoDB database setup and configured.
*   Appropriate middleware for handling requests (e.g., `express.json()`, `multer` for file uploads, authentication middleware for user verification).

**API Endpoints:**

The following API endpoints are supported:

*   `POST /crime-reports`: Creates a new crime report.  Requires authentication. Expects data in `req.body` and evidence files in `req.files` (if multipart/form-data).
*   `GET /crime-reports`: Retrieves crime reports for the logged-in user. Requires authentication.
*   `GET /crime-reports/all`: Retrieves all crime reports (requires appropriate permissions/role-based access control).
*   `PUT /crime-reports/:id/assign-officer`: Assigns an officer to a crime report. Requires authentication and officer ID (in `req.body`) or defaults to the logged-in user.
*   `PUT /crime-reports/:id/status`: Updates the status of a crime report.  Requires authentication and the desired status in `req.body`.

**Example Usage:**

```javascript
// Example in Express.js app.js or routes
import express from 'express';
import { createCrimeReport, getCrimeReports, getAllReports, assignOfficer, updateStatus } from './crime.controllers.js'; // Assuming you have an index.js which exports these controllers.
import multer from 'multer';

const router = express.Router();
const upload = multer({ dest: 'uploads/' }); // configure as needed

// Authentication middleware (example)
const authenticate = (req, res, next) => {
    // Implement your authentication logic here
    // For example:
    // if (!req.user) return res.status(401).json({ message: 'Unauthorized' });
    next();
};

router.post('/crime-reports', authenticate, upload.array('evidence'), createCrimeReport);
router.get('/crime-reports', authenticate, getCrimeReports);
router.get('/crime-reports/all', getAllReports); // Note: Should probably be protected with authentication and authorization
router.put('/crime-reports/:id/assign-officer', authenticate, assignOfficer);
router.put('/crime-reports/:id/status', authenticate, updateStatus);

export default router;
```

## Technologies Used

*   Node.js
*   Express.js
*   MongoDB (via Mongoose, implied)
*   Multer (for file uploads)
*   JavaScript

## Architecture or Code Overview

The `crime.controllers.js` file exports several asynchronous functions, each designed to handle a specific action related to crime reports.

*   **`createCrimeReport`**: Handles creation of new crime reports. Parses the request body which may contain `crimeData` (JSON) and `evidence` (files), validates data, creates a `CrimeReport` document, saves it to the database, and returns the saved report with populated user details. Includes a helper function `detectFileType` for determining the file type based on the MIME type.
*   **`getCrimeReports`**: Retrieves crime reports associated with the currently authenticated user. Uses `CrimeReport.find()` with population to retrieve the reports.
*   **`getAllReports`**: Retrieves all crime reports. This requires appropriate access control to be implemented.
*   **`assignOfficer`**: Assigns an officer to a crime report.
*   **`updateStatus`**: Updates the status of a crime report (e.g., 'pending', 'investigating', 'resolved', 'closed').

## Known Issues / Improvements

*   **Error Handling:** Improve error handling and provide more informative error messages.
*   **Input Validation:** Implement robust input validation to prevent data injection and ensure data integrity.
*   **Authentication & Authorization:** The `authenticate` middleware is a placeholder and should be implemented with a secure authentication and authorization mechanism. Implement role based access control (RBAC).
*   **File Storage:** Consider using a cloud storage service (e.g., AWS S3, Google Cloud Storage, Azure Blob Storage) instead of local storage for file uploads.
*   **Security:** Implement security best practices, such as sanitizing inputs to prevent injection attacks.
*   **Testing:** Implement unit and integration tests.

## Additional Notes or References

*   The code interacts with a `CrimeReport` model (assumed to be in `../models/crime.model.js`).
*   The code utilizes `multer` middleware for handling file uploads. Ensure the configuration matches the needs of the application (file size limits, accepted file types, storage locations, etc.).
*   Consider implementing a proper logging system for monitoring and debugging.
*   Implement appropriate rate limiting to prevent abuse.