# Crime Master - Authentication Controllers

## Folder Structure

```
├── auth.controllers.js
```

## Description

This module provides the authentication controllers for the Crime Master application. It handles user signup, login, and logout functionalities, including security measures like password hashing and token generation. It also includes special handling for a police role with fixed credentials, preventing standard signup via the public endpoint.

## How to Use

This module is used internally by the application's routing and authentication middleware. It is not intended for direct use.

## Technologies Used

*   **Languages:** JavaScript
*   **Libraries:**
    *   bcryptjs (for password hashing)
    *   jsonwebtoken (for token generation - assumed from `generateToken` usage)
    *   cookie-parser (for setting and managing cookies - assumed from the code using `res.cookie`)

## Architecture or Code Overview

The module exports three main functions:

1.  `signUp`:
    *   Validates required fields (firstname, lastname, email, password, username).
    *   Prevents signup as 'police' (based on a configurable POLICE\_ID).
    *   Checks for existing users.
    *   Hashes the password using `bcrypt`.
    *   Creates a new user in the database (assumed to use a `User` model).
    *   Generates a JWT token.
    *   Sets an HTTP-only cookie to store the token.
    *   Returns a success message with user details.

2.  `login`:
    *   Validates that username/email and password are provided.
    *   Handles police login (using fixed credentials if the username or email matches `POLICE_ID` and password matches `POLICE_PWD`).
    *   Finds a user by username or email.
    *   Compares the provided password with the stored password using `bcrypt`.
    *   Generates a JWT token.
    *   Sets an HTTP-only cookie to store the token.
    *   Returns a success message with user details.

3.  `logout`:
    *   Clears the authentication token cookie.
    *   Returns a success message.

## Known Issues / Improvements

*   Error handling could be enhanced with more specific error messages and logging.
*   Consider adding input validation to prevent security vulnerabilities (e.g., input sanitization).
*   Implement refresh tokens for better security.

## Additional Notes or References

This module is part of the Crime Master web application.