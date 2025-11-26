# Crime Report Model

## Description

This project defines the Mongoose schema for a crime report in a MERN stack web application. It outlines the structure for storing and managing crime-related information, including details about the incident, location, involved parties, evidence, and status updates.

## Technologies Used

*   JavaScript
*   Node.js
*   Mongoose

## Architecture or Code Overview

The `crime.model.js` file defines the `CrimeReport` Mongoose model.

*   `crimeReportSchema`:  Defines the structure of a crime report document, including fields for title, description, location, incident date, reporter, status, evidence, witnesses, assigned officer, and updates.
*   `CrimeReport`: The Mongoose model based on the `crimeReportSchema`.

### Key Fields

*   `title`:  Title of the crime report.
*   `description`: Description of the crime.
*   `location`:  Nested object with address details (address, city, state, pincode).
*   `incidentDate`:  Date of the incident.
*   `reportedBy`:  Reference to the 'User' model (reporter).
*   `status`:  Current status of the report (pending, investigating, resolved, closed).
*   `evidence`:  Array of evidence objects (type, url, description).
*   `witnesses`: Array of witness objects (name, contact, statement).
*   `assignedOfficer`: Reference to the 'User' model (police officer).
*   `updates`: Array of updates with message, updatedBy (User reference), and timestamp.
*   `timestamps`: Enables automatic creation of `createdAt` and `updatedAt` timestamps.

## Known Issues / Improvements

*   Implement validation for URL formats in `evidence.url`.
*   Consider adding geolocation data for the location.
*   Enhance error handling and data sanitization.

## Additional Notes or References

This model is designed to be used in conjunction with a User model (referenced in `reportedBy` and `assignedOfficer`) within a MERN stack application.