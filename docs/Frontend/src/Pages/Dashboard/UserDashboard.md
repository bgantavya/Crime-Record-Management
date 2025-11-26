# Crime Management System - Citizen Dashboard

## Description

The Crime Management System (CMS) provides a web-based platform for citizens to report crimes, track case statuses, and communicate with law enforcement. This component, `UserDashboard.jsx`, implements the user dashboard, offering an overview of recent activities, active cases, and access to various features like filing reports, accessing messages, and managing settings.

## Folder Structure

```
├── UserDashboard.jsx
└── ... (other project files)
```

## How to Use

1.  **Installation:**

    This component is part of a larger React application. Ensure you have the necessary dependencies installed. Refer to the project's root `README.md` for installation instructions.

2.  **Usage:**

    The `UserDashboard` component is designed to be rendered within the application's routing structure. It leverages context for user data and utilizes React Router for navigation.  Access the dashboard through the route defined in your application's router (e.g., `/dashboard/user`). The component uses mock data for demonstration purposes, replace with real data fetching in the final version.

## Technologies Used

*   **React:** JavaScript library for building user interfaces.
*   **React Router:** For navigation and routing.
*   **Context API:**  For state management (`dataContext`).
*   **Tailwind CSS:** Utility-first CSS framework for styling.
*   **JavaScript (ES6+):**  Programming language.

## Architecture or Code Overview

*   **`UserDashboard` Component:**
    *   Manages the overall structure of the user dashboard.
    *   Retrieves user data using `useContext` from `dataContext`.
    *   Uses the `useState` hook for managing the currently active tab.
    *   Employs `useNavigate` from `react-router-dom` for navigation between different sections of the dashboard.
    *   Renders a header, sidebar navigation, and main content area.
    *   The `renderTabContent` function dynamically renders the content for each tab based on the `activeTab` state.
*   **`OverviewTab` Component:**
    *   Displays an overview of the user's dashboard data.
    *   Renders stats, recent activity, and active cases using mock data.
    *   Displays data in a well-structured grid layout.

## Known Issues / Improvements

*   **Data Fetching:** The component currently uses mock data. Implement data fetching from a backend API to populate the dashboard with real data.
*   **Dynamic Content:** Implement the actual content for report, cases, message, resources, and settings pages (linked in the navigation).
*   **User Authentication:**  Integrate proper user authentication and authorization to secure access to the dashboard and its features.
*   **Error Handling:** Implement error handling and loading states for data fetching.

## Additional Notes or References

*   This component is part of a larger project; see the project's main `README.md` for overall context and project setup.
*   The UI is built using Tailwind CSS for styling.