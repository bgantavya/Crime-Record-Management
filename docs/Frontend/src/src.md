# Crime Master

## Folder Structure

```
├── Pages
│   ├── Auth
│   │   ├── Login.jsx
│   │   └── SignUp.jsx
│   └── Dashboard
│       ├── Messages.jsx
│       ├── MyCases.jsx
│       ├── PoliceDashboard.jsx
│       ├── ReportCrime.jsx
│       ├── Resources.jsx
│       ├── Settings.jsx
│       └── UserDashboard.jsx
├── context
│   └── usercontex.jsx
├── App.jsx
└── main.jsx
```

## Description

A MERN-based web application designed for reporting and managing crime records. It features two user roles: User and Police.

## How to Use

1.  **Installation:**

    *   Clone the repository.
    *   Navigate to the project directory.
    *   Run `npm install` or `yarn install` to install dependencies.
2.  **Running the Application:**

    *   Run `npm start` or `yarn start` to start the development server.
    *   Open your browser and navigate to `http://localhost:3000` (or the port specified by the development server).

## Technologies Used

*   React
*   Node.js
*   Express.js
*   MongoDB
*   JavaScript
*   HTML
*   CSS

## Architecture or Code Overview

*   **`App.jsx`**: Main application component, manages routing.
*   **`main.jsx`**: Entry point of the React application, renders the `App` component.
*   **`Pages/Auth/Login.jsx`**: Handles user login functionality.
*   **`Pages/Auth/SignUp.jsx`**: Handles user registration functionality.
*   **`Pages/Dashboard/*`**: Components for different dashboard views (MyCases, ReportCrime, etc.).
*   **`context/usercontex.jsx`**: Manages user authentication state.

## Known Issues / Improvements

*   Implement database integration.
*   Implement backend API endpoints.
*   Implement robust user authentication and authorization.
*   Improve UI design and responsiveness.

## Additional Notes or References

*   **Authors:** Gantavya Bansal
*   **Keywords:** MERN, crime reporting, web application