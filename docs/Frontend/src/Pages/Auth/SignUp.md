# Crime Master - Sign Up

## Description

The SignUp component provides a user interface for new users to register for the Crime Master application. It allows users to create an account by providing their personal information, and it handles the submission of this data to the backend for account creation. It includes features like input validation, visual feedback during loading, and a restriction to prevent the police ID or "police" as a username/email.

## How to Use

1.  **Navigate to the Sign Up Page:** Ensure you are on the sign up route of the application.
2.  **Fill the Form:** Enter your first name, last name, username, email address, and password in the respective fields.
3.  **Agree to Terms and Privacy:** Check the box to agree to the terms of service and privacy policy.
4.  **Submit the Form:** Click the "Create Account" button.
5.  **Confirmation:** Upon successful registration, you will receive a success message, and you will be redirected to the dashboard.

## Technologies Used

*   **React:** Frontend library for building the user interface.
*   **React Router:** For navigation and routing within the application.
*   **Axios:** For making HTTP requests to the backend API.
*   **Tailwind CSS:** For styling the user interface.
*   **Context API:** For state management using user data context

## Architecture or Code Overview

*   **State Management:** The component uses the `useState` hook to manage the form input fields (firstname, lastname, username, email, password) and the loading state (`isLoading`).
*   **Context API:** Uses the `dataContext` to access `serverUrl`
*   **Event Handling:** The `handlesubmit` function is triggered when the form is submitted.
*   **Validation:**  Checks for empty fields and prevents registration with police credentials.
*   **API Call:** Makes a POST request to the `/api/signup` endpoint using `axios` to submit the registration data to the backend.
*   **Error Handling:** Catches and displays errors from the server.
*   **Navigation:** Uses `useNavigate` to redirect to the dashboard after successful signup.
*   **UI:** Implements a Tailwind CSS based UI for the sign-up form with visual enhancements, including animated backgrounds and loading indicators.

## Known Issues / Improvements

*   Implement proper form validation on the client and server side.
*   Improve error messages for user-friendliness.
*   Add password strength validation.

## Additional Notes or References
*   This component is part of the Crime Master web application.
*   The `serverUrl` is obtained from the `dataContext`, which should be configured in a parent component.