# Crime Master - Frontend

## Folder Structure

```
├── public
├── src
│   ├── Pages
│   │   ├── Auth
│   │   │   ├── Login.jsx
│   │   │   └── SignUp.jsx
│   │   └── Dashboard
│   │       ├── Messages.jsx
│   │       ├── MyCases.jsx
│   │       ├── PoliceDashboard.jsx
│   │       ├── ReportCrime.jsx
│   │       ├── Resources.jsx
│   │       ├── Settings.jsx
│   │       └── UserDashboard.jsx
│   ├── context
│   │   └── usercontex.jsx
│   ├── App.jsx
│   └── main.jsx
└── index.html
```

## Description

A MERN (MongoDB, Express.js, React, Node.js) based web application designed for reporting and managing crime records. It features two user roles: User and Police.

## How to Use

1.  **Prerequisites:** Node.js and npm/yarn installed.
2.  **Installation:**

    *   Navigate to the project directory in your terminal.
    *   Run `npm install` or `yarn install` to install dependencies.
3.  **Running the Application:**

    *   Run `npm start` or `yarn start` to start the development server.
    *   Open your browser and navigate to `http://localhost:3000` (or the port specified by the development server).

## Technologies Used

*   React
*   JavaScript (ES6+)
*   HTML
*   CSS

## Architecture or Code Overview

*   **`src/`:** Contains the main source code.
    *   **`Pages/`:** Contains components for different pages, including authentication (Login, SignUp) and dashboard components for both User and Police roles.
    *   **`context/`:**  Contains the `usercontex.jsx` for managing user authentication state.
    *   **`App.jsx`:** The main application component, likely handling routing and overall structure.
    *   **`main.jsx`:** Entry point for the React application.
*   **`public/`:** Contains static assets and the `index.html` file.

## Known Issues / Improvements

*   Implement user authentication and authorization logic.
*   Develop backend APIs for data management.
*   Enhance UI/UX for improved user experience.
*   Add data validation and error handling.

## Additional Notes or References

*   **Authors:** Gantavya Bansal
*   **Keywords:** MERN, crime reporting, web application