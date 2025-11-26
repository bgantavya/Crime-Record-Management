# Crime Master - Auth Middleware

## Folder Structure

```
├── auth.middleware.js
```

## Description

This middleware provides authentication functionalities for the Crime Master web application. It is designed to verify user authentication before allowing access to protected resources.

## How to Use

The middleware can be integrated into your MERN stack application's routing to protect specific routes.

Example usage (Node.js/Express):

```javascript
const express = require('express');
const { authenticateToken } = require('./auth.middleware'); // Assuming auth.middleware.js is in the same directory
const app = express();

app.get('/protectedRoute', authenticateToken, (req, res) => {
  // Access to this route is only granted if the user is authenticated.
  res.json({ message: 'Access granted!' });
});
```

The `authenticateToken` function is expected to:

1.  Extract the token from the request headers (e.g., Authorization header).
2.  Verify the token's validity (e.g., using JWT verification).
3.  If valid, attach the user's information to the `req` object (e.g., `req.user`).
4.  Call `next()` to proceed to the route handler.
5.  If invalid or missing, return an appropriate error response (e.g., 401 Unauthorized).

## Technologies Used

*   Node.js
*   Express.js
*   JWT (JSON Web Tokens) - Used for token generation and verification

## Architecture or Code Overview

The `auth.middleware.js` file likely contains a function (`authenticateToken` in the example) that performs the following steps:

1.  **Token Extraction**: Retrieves the authentication token from the request headers.
2.  **Token Verification**: Validates the token's signature, expiry, and other claims, typically using a library like `jsonwebtoken`.
3.  **User Identification**:  If the token is valid, it decodes the token to retrieve user information (e.g., user ID, roles).
4.  **Request Enrichment**: Attaches the user information to the request object, making it accessible to subsequent route handlers (e.g., `req.user`).
5.  **Authorization**: Based on user roles or permissions, access to specific resources can be granted or denied within the route handlers.

## Known Issues / Improvements

*   Implement proper error handling for invalid or expired tokens.
*   Add role-based authorization for finer-grained access control.
*   Consider implementing token refresh functionality.

## Additional Notes or References

*   **Authors**: Gantavya Bansal
*   **Keywords**: MERN, webapp, crime, user, police