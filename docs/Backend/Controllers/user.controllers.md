# Crime Master - User Controllers

## Description

This project provides user controller functions for the Crime Master web application. It handles user-related API requests.

## How to Use

The `me` function retrieves user information for the currently authenticated user.

### API Endpoint

*   `/me`: Returns user details.

## Technologies Used

*   JavaScript
*   Node.js
*   Express.js (Implied)

## Architecture or Code Overview

The `user.controllers.js` file contains a single function:

*   `me`:
    *   Authenticates the user using `req.user`.
    *   Returns the user's details (firstname, lastname, username, email, role) if authenticated.
    *   Returns a 401 Unauthorized status if not authenticated.
    *   Returns a 500 Server Error status on any other error.

## Known Issues / Improvements

*   Error handling could be improved with more specific error messages.
*   Consider adding validation for user data before returning.

## Additional Notes or References

This file is part of a larger MERN stack web application.