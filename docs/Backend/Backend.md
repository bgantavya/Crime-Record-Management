# Crime Master - Backend

## Folder Structure

```
├── Controllers
│   ├── auth.controllers.js
│   ├── crime.controllers.js
│   └── user.controllers.js
├── middleware
│   └── auth.middleware.js
├── models
│   ├── crime.model.js
│   └── user.model.js
├── public
└── index.js
```

## Description

The backend for Crime Master, a MERN-based web application designed for crime record reporting and management. It supports two roles: User and Police.

## How to Use

1.  **Installation:**

    *   Clone the repository.
    *   Navigate to the project directory.
    *   Install dependencies using `npm install`.

2.  **Running the Application:**

    *   Start the server using `node index.js`.

3.  **API Usage:**

    *   API endpoints are available for user authentication, crime reporting, and crime record management.

## Technologies Used

*   Node.js
*   Express.js
*   MongoDB
*   Mongoose
*   (Additional technologies inferred from code: JWT, bcrypt)

## Architecture or Code Overview

*   **Controllers:** Handle incoming requests and interact with the models.
    *   `auth.controllers.js`: Manages user authentication (login, signup).
    *   `crime.controllers.js`: Handles crime record creation, retrieval, and updates.
    *   `user.controllers.js`: Manages user-related operations.
*   **Middleware:**  Acts as an intermediary between requests and the application, e.g. authentication.
    *   `auth.middleware.js`:  Authenticates users.
*   **Models:** Define the structure and schema for data storage in MongoDB.
    *   `crime.model.js`: Defines the schema for crime records.
    *   `user.model.js`: Defines the schema for user data.
*   `index.js`:  Entry point of the application, sets up the server, connects to the database, and defines routes.

## Known Issues / Improvements

*   Implement proper error handling throughout the application.
*   Add comprehensive unit and integration tests.
*   Enhance security measures (e.g., input validation, rate limiting).
*   Implement data validation.
*   Add more features like role-based access control.

## Additional Notes or References

*   Authors: Gantavya Bansal