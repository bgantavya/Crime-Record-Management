# Crime Master

## Folder Structure

```
├── Backend
│   ├── Controllers
│   │   ├── auth.controllers.js
│   │   ├── crime.controllers.js
│   │   └── user.controllers.js
│   ├── middleware
│   │   └── auth.middleware.js
│   ├── models
│   │   ├── crime.model.js
│   │   └── user.model.js
│   ├── public
│   └── index.js
└── Frontend
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

A MERN stack web application designed for reporting and managing crime records. It features two user roles: user and police.

## How to Use

### Frontend

1.  **Installation:**

    ```bash
    cd Frontend
    npm install
    ```

2.  **Running the Frontend:**

    ```bash
    cd Frontend
    npm run dev
    ```

### Backend

1.  **Installation:**

    ```bash
    cd Backend
    npm install
    ```

2.  **Running the Backend:**

    ```bash
    cd Backend
    node index.js
    ```

## Technologies Used

*   **Frontend:** React, JavaScript, HTML, CSS
*   **Backend:** Node.js, Express.js, MongoDB
*   **Other:** Mongoose

## Architecture or Code Overview

### Frontend

*   **`src/Pages/Auth`**: Contains the Login and SignUp components.
*   **`src/Pages/Dashboard`**: Contains components for user dashboards, including messages, my cases, police dashboard, report crime, resources and settings.
*   **`src/context/usercontex.jsx`**: Manages user context.
*   **`App.jsx`**: Main application component.
*   **`main.jsx`**: Entry point for the React application.

### Backend

*   **`Controllers`**: Handles request logic.
    *   `auth.controllers.js`: Authentication logic.
    *   `crime.controllers.js`: Crime-related operations.
    *   `user.controllers.js`: User-related operations.
*   **`middleware`**: Contains authentication middleware.
    *   `auth.middleware.js`: Handles authentication middleware.
*   **`models`**: Defines data models.
    *   `crime.model.js`: Crime model.
    *   `user.model.js`: User model.
*   **`index.js`**: Main entry point for the backend server.

## Known Issues / Improvements

*   Implement proper error handling.
*   Add more comprehensive tests.
*   Improve UI/UX.
*   Implement role based authorization.

## Additional Notes or References

*   **Authors:** Gantavya Bansal
*   **Keywords:** MERN, crime reporting, web application