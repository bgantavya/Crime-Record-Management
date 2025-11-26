# Crime Master - Authentication Middleware

## Folder Structure

*(No folder structure provided, assuming a simple file structure.)*

*   `auth.middleware.js`

## Description

This middleware provides authentication and authorization functionalities for the Crime Master web application. It handles token-based authentication using JSON Web Tokens (JWT) and role-based authorization to restrict access to certain routes.

## How to Use

1.  **Installation:**

    Ensure that the required dependencies (`jsonwebtoken`) are installed.  Also ensure that the User model is available as `../models/user.model.js`.

    ```bash
    npm install jsonwebtoken
    ```

2.  **Usage:**

    Import the middleware functions into your route handlers:

    ```javascript
    import { authenticate, requirePolice } from './auth.middleware.js';
    ```

    Use `authenticate` middleware to protect routes that require authentication:

    ```javascript
    app.get('/protected', authenticate, (req, res) => {
      res.json({ message: 'Authenticated', user: req.user });
    });
    ```

    Use `requirePolice` middleware to restrict access to police users only:

    ```javascript
    app.get('/police-only', authenticate, requirePolice, (req, res) => {
      res.json({ message: 'Police access granted' });
    });
    ```

## Technologies Used

*   JavaScript
*   Node.js
*   `jsonwebtoken` library

## Architecture or Code Overview

*   `authenticate`:
    *   Retrieves the JWT from the `token` cookie.
    *   Verifies the token's validity using `jwt.verify()` and the `JWT_SECRET` environment variable.
    *   If the token is valid, it retrieves the user from the database using the user ID extracted from the token. The password is not selected.
    *   Sets `req.user` to the authenticated user object.
    *   Handles cases where a police-officer ID is used.
    *   Returns 401 Unauthorized if authentication fails.
*   `requirePolice`:
    *   Checks if the user has been authenticated (`req.user` exists).
    *   Verifies if the user's role is 'police' or the username matches the `POLICE_ID` or "police-officer".
    *   Returns 403 Forbidden if the user does not have police role.

## Known Issues / Improvements

*   Error handling could be enhanced to provide more specific error messages.
*   Consider implementing refresh token functionality for improved security.
*   Refactor to decouple authentication and user model interactions.

## Additional Notes or References

*   Requires the `JWT_SECRET` and optionally `POLICE_ID` environment variables to be set.
*   Part of the Crime Master web application.