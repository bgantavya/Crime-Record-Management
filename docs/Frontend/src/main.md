# Crime Master

## Folder Structure

```
├── README.md
├── index.css
├── App.jsx
├── context/
│   └── usercontex.jsx
└── main.jsx
```

## Description

A MERN stack web application designed for reporting and managing crime records. It features two user roles: user and police.

## How to Use

1.  **Installation:**

    *   Ensure you have Node.js and npm installed.
    *   Navigate to the project directory in your terminal.
    *   Run `npm install` to install dependencies.

2.  **Running the Application:**

    *   Run `npm start` to start the development server.
    *   Open your web browser and go to `http://localhost:3000` (or the port specified by your development server).

## Technologies Used

*   React
*   React Router
*   JavaScript (ES6+)
*   HTML
*   CSS

## Architecture or Code Overview

The application utilizes React for the user interface.

*   `main.jsx`: Entry point for the React application, rendering the `App` component within a `BrowserRouter` and `UserContext`.
*   `App.jsx`: The main application component, likely handling routing and overall structure.
*   `usercontex.jsx`: Manages user-related context (authentication, roles, etc.).

## Known Issues / Improvements

*   Implement the backend (MERN stack).
*   Add proper user authentication and authorization.
*   Implement data fetching and storage.
*   Improve styling and user experience.

## Additional Notes or References

*   This project is developed by Gantavya Bansal.