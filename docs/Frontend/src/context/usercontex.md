# Crime Master - User Context

## Folder Structure

*(No folder structure provided)*

## Description

This project provides a React context (`UserContext`) to manage and share user authentication data across a React application. It fetches the current user's information from a backend server and makes it available to all child components.

## How to Use

1.  **Installation:**

    No specific installation steps are required for the `UserContext` component itself, as it's meant to be integrated into a React application.  Ensure you have `axios` installed:
    ```bash
    npm install axios
    ```

2.  **Usage:**

    Wrap your application or the relevant components with the `UserContext.Provider`:

    ```jsx
    import UserContext from './usercontex'; // Assuming usercontex.jsx is in the same directory

    function App() {
      return (
        <UserContext>
          {/* Your application components */}
        </UserContext>
      );
    }
    ```

    Access the context values within child components using `useContext`:

    ```jsx
    import { useContext } from 'react';
    import { dataContext } from './usercontex';

    function MyComponent() {
      const { currentUser, serverUrl, refreshUser } = useContext(dataContext);

      // Use currentUser, serverUrl, and refreshUser as needed
      return (
          <div>
              {currentUser ? `Welcome, ${currentUser.name}` : 'Please log in'}
          </div>
      );
    }
    ```

## Technologies Used

*   **React:** JavaScript library for building user interfaces.
*   **JavaScript (ES6+):** Programming language.
*   **Axios:** Promise-based HTTP client for making API requests.
*   **React Context API:**  For state management and sharing data between components.

## Architecture or Code Overview

*   **`dataContext`:**  A React Context created using `createContext()` to hold and provide user-related data.
*   **`UserContext` Component:**
    *   Uses `useState` to manage the `currentUser` state.
    *   Uses `useEffect` to fetch the current user's data on component mount using `fetchCurrentUser`.
    *   `fetchCurrentUser`: An asynchronous function to retrieve user data from the backend server using Axios. It handles potential errors and sets `currentUser` accordingly.
    *   Provides the `serverUrl`, `currentUser`, and `refreshUser` (a function to refetch user data) through the `dataContext.Provider`.
*   **`serverUrl`**:  Defines the base URL for the backend API.
*   **`currentUser`**:  Stores the current user's data (or `null` if not logged in).
*   **`refreshUser`**:  A function that triggers a re-fetch of user data. Useful for updating the user context after login/logout operations in other components.

## Known Issues / Improvements

*   **Error Handling:**  Improved error handling within `fetchCurrentUser` (e.g., displaying user-friendly error messages).
*   **Security:**  Consider more robust handling of authentication tokens and potential security vulnerabilities.
*   **Backend Integration:** Assumes a backend API endpoint at `/api/me`.  Adjust the server URL if necessary.

## Additional Notes or References

*   This context assumes a server-side authentication mechanism where the server sets authentication cookies (e.g. `withCredentials: true` in the axios call).
*   Based on the project description this context manages user authentication for the "Crime Master" webapp