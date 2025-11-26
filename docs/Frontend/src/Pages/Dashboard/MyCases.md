# MyCases

## Description

This React component, `MyCases`, displays a list of mock crime cases. It allows users to filter cases by status (all, pending, investigating, evidence_required, resolved) and search cases by title or ID.  The component uses mock data to represent cases with details like title, status, priority, assigned officer, description, updates, and more.  It's styled with Tailwind CSS for a modern and responsive user interface.

## How to Use

1.  **Prerequisites:** Ensure you have Node.js and npm (or yarn) installed.  Also, this component depends on Tailwind CSS for styling.

2.  **Installation:**

    *   Create a React project using `create-react-app` if you don't have one:
        ```bash
        npx create-react-app my-cases-app
        cd my-cases-app
        ```

    *   Install Tailwind CSS and its peer dependencies:
        ```bash
        npm install -D tailwindcss postcss autoprefixer
        npx tailwindcss init -p
        ```

    *   Configure your template paths in `tailwind.config.js`:
        ```javascript
        /** @type {import('tailwindcss').Config} */
        module.exports = {
          content: [
            "./src/**/*.{js,jsx,ts,tsx}",
          ],
          theme: {
            extend: {},
          },
          plugins: [],
        }
        ```

    *   Add Tailwind directives to your `index.css` or `src/App.css` file:
        ```css
        @tailwind base;
        @tailwind components;
        @tailwind utilities;
        ```

3.  **Integrate the component:**

    *   Place the `MyCases.jsx` file inside your React project's `src` folder.

    *   Import and use the component within your app, e.g., in `src/App.js`:

        ```javascript
        import React from 'react';
        import MyCases from './MyCases';

        function App() {
          return (
            <MyCases />
          );
        }

        export default App;
        ```

4.  **Run the application:**

    ```bash
    npm start
    ```

    This will start the development server, and you can view the component in your web browser, typically at `http://localhost:3000`.

## Technologies Used

*   **React:** JavaScript library for building user interfaces.
*   **Tailwind CSS:**  A utility-first CSS framework for styling.
*   **JavaScript (ES6+):**  Programming language.
*   **useState Hook:** React Hook for managing component state.

## Architecture or Code Overview

*   **`MyCases` Component:**
    *   **State:**
        *   `filter`:  String representing the current filter (e.g., 'all', 'pending').  Initialized to 'all'.
        *   `searchTerm`: String representing the search term. Initialized to an empty string.
    *   **`cases` Data:** A constant array containing mock case data, including: `id`, `title`, `status`, `priority`, `assignedOfficer`, `dateReported`, `lastUpdate`, `description`, and `updates`.
    *   **`filteredCases` Calculation:** Filters the `cases` data based on the current `filter` and `searchTerm`.
    *   **`getStatusColor(status)` Function:** Returns Tailwind CSS classes for status-based styling (background and text colors).
    *   **`getPriorityColor(priority)` Function:** Returns Tailwind CSS classes for priority-based styling (text colors).
    *   **JSX Structure:**
        *   A main container with a gradient background and padding.
        *   A wrapper with a background and rounded corners.
        *   A header with title, description, filter buttons, and search input.
        *   Mapping `filteredCases` to render individual case items, displaying case details like the header (title, status, priority, officer), description, timeline (reported & last update), and case updates.
        *   Conditionally renders "No cases found" message if `filteredCases` is empty.

## Known Issues / Improvements

*   **Data Source:** The current implementation uses mock data. In a real application, the data would come from an API or database.
*   **Functionality:**  The "Send Message", "View Details", and "Upload Evidence" buttons are currently placeholders and do not have any functionality.
*   **Error Handling:** No error handling implemented for data loading or other potential issues.
*   **Responsiveness:** While using Tailwind, further optimization of the layout for various screen sizes might be needed.
*   **Accessibility:** Consider adding ARIA attributes for better accessibility.

## Additional Notes or References

*   The component uses Tailwind CSS for all styling.
*   This is a front-end UI component example, not a full-fledged application.