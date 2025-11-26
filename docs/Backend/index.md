# Crime Master

## Folder Structure

```
├── Backend
│   ├── Config
│   │   └── db.js
│   ├── Routes
│   │   ├── auth.routes.js
│   │   └── crime.routes.js
│   ├── uploads
│   ├── index.js
│   └── ...
└── ...
```

## Description

A MERN (MongoDB, Express.js, React, Node.js) web application for reporting and managing crime records. It features two user roles: User and Police.

## How to Use

1.  **Installation:**

    *   Clone the repository.
    *   Navigate to the backend directory `cd Backend`.
    *   Run `npm install` to install the dependencies.
    *   Set up a `.env` file with the following variables:
        *   `MONGO_URI`: Your MongoDB connection string.
        *   `PORT`: The port on which the server will run (e.g., `8000`).
        *   `JWT_SECRET`: A secret key for JWT authentication.
        *   `COOKIE_SECRET`: A secret key for cookie encryption.
        *   `CLOUDINARY_CLOUD_NAME`: Cloudinary cloud name.
        *   `CLOUDINARY_API_KEY`: Cloudinary API key.
        *   `CLOUDINARY_API_SECRET`: Cloudinary API secret.
    *   Run `node index.js` or `npm start` to start the server.

2.  **API Usage:**

    *   The backend exposes the following API endpoints:
        *   `/api/register`: User registration.
        *   `/api/login`: User login.
        *   `/api/logout`: User logout.
        *   `/api/crime`: Crime-related endpoints (CRUD operations).
    *   Use a tool like Postman or Insomnia to interact with the API endpoints.

## Technologies Used

*   **Node.js:** JavaScript runtime environment.
*   **Express.js:** Web application framework.
*   **MongoDB:** NoSQL database.
*   **Mongoose:** MongoDB object modeling tool.
*   **dotenv:** For loading environment variables.
*   **cookie-parser:** Middleware for parsing cookies.
*   **cors:** Middleware for enabling CORS.
*   **JWT:** For authentication.
*   **Cloudinary:** For file upload (Images, Videos).

## Architecture or Code Overview

*   **`index.js`**: Main entry point, sets up the Express application, middleware, and routes.
*   **`Config/db.js`**: Connects to the MongoDB database.
*   **`Routes/auth.routes.js`**: Handles authentication-related routes (register, login, logout).
*   **`Routes/crime.routes.js`**: Handles crime record-related routes (CRUD operations).
*   **Middleware**: Uses `express.json()`, `cookieparser()`, and `cors()` for request parsing and cross-origin resource sharing.
*   **CORS**: Configured to allow requests from `https://crime-record-management-4.onrender.com`.

## Known Issues / Improvements

*   Implement proper error handling throughout the application.
*   Add input validation to all API endpoints.
*   Implement user roles and permissions for access control.
*   Improve database schema design for better efficiency and scalability.
*   Implement frontend.

## Additional Notes or References

*   This project is a MERN stack application.
*   Uses Cloudinary for file uploads.
*   The backend is configured to serve static files from the `uploads` directory.