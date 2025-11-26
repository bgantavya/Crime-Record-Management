# Crime Master - Login Component

## Description

The `Login.jsx` component provides a secure and user-friendly interface for user and police officer login within the Crime Master web application.  It allows users to authenticate with either a username/password or email/password combination (for standard users) and enforces specific credentials for police officers.  The component includes a visually appealing UI with animated background elements and role-specific login options.

## Folder Structure

```
- context/
    - usercontex.jsx
- Login.jsx
```

## How to Use

1.  **Installation**:  The component is part of a larger React application. Ensure the necessary dependencies are installed as per the project's requirements. This component uses `react-router-dom` and `axios`.
2.  **Integration**:  Import and render the `Login` component within your application's routing structure.
3.  **Usage**:
    *   Navigate to the login route (e.g., `/login`).
    *   Select the role ("Citizen" or "Police Officer").
    *   Enter the required credentials (username/password or email/password).  Police officers are provided with a pre-filled Officer ID.
    *   Click the "Login" button.  The application will attempt to authenticate the user and redirect to the appropriate dashboard on successful login (`/dashboard/user` or `/dashboard/police`).

## Technologies Used

*   **React**:  JavaScript library for building user interfaces.
*   **React Router Dom**: For handling routing and navigation.
*   **Axios**:  Promise-based HTTP client for making API requests.
*   **JavaScript (ES6+)**:  Programming language.
*   **HTML/JSX**:  Markup language.
*   **CSS (Tailwind CSS)**: For styling.

## Architecture or Code Overview

*   **State Management**:  Uses React's `useState` hook to manage the following:
    *   `username`:  The user's username.
    *   `email`: The user's email.
    *   `password`:  The user's password.
    *   `useEmail`:  A boolean flag to determine whether to login using email or username.
    *   `loginAs`:  A string specifying the user's role (`user` or `police`).
    *   `isLoading`:  A boolean flag to indicate loading state during the login process.
*   **Context**: Uses `dataContext` from `usercontex.jsx` to access `serverUrl`.
*   **`handleSubmit` function**:
    *   Prevents default form submission behavior.
    *   Sets `isLoading` to true.
    *   Constructs the payload based on selected role and login method (username/password or email/password).
    *   Makes a POST request to the `/api/login` endpoint using `axios`.
    *   Handles successful login by navigating to the appropriate dashboard (`/dashboard/user` or `/dashboard/police`).
    *   Handles login errors by displaying an alert message.
    *   Sets `isLoading` to false in a `finally` block to ensure loading state is cleared.
*   **`fillPolice` function**: Pre-fills the form with police officer credentials for demonstration.
*   **`fillDemoUser` function**: Pre-fills the form with demo user credentials.
*   **UI Components**:  The component includes:
    *   Role selection buttons ("Citizen" and "Police Officer").
    *   Input fields for username/email and password.
    *   A "Login" button.
    *   Visual feedback during the login process (loading indicator).
    *   UI elements for demonstration of login process.
    *   Links to registration pages.
*   **Styling**: Utilizes Tailwind CSS for styling and layout.

## Known Issues / Improvements

*   **Error Handling**:  Improve the error message display.
*   **Security**: Implement more robust input validation and sanitization.
*   **Accessibility**:  Ensure the component meets accessibility standards (e.g., ARIA attributes).
*   **UI Enhancements**: Refactor the component into smaller subcomponents.

## Additional Notes or References

*   This component integrates with a backend API (assumed to be at `${serverUrl}/api/login`).  Ensure that the backend is properly configured to handle login requests.
*   The `withCredentials: true` option in the `axios` request is crucial for managing cookies and maintaining user sessions.
*   The use of `alert()` for displaying error messages should be replaced with a more user-friendly mechanism.