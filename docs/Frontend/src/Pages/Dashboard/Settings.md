# Settings Component

## Description

This React component provides a settings interface for managing user profile information and notification preferences. It includes profile information editing and notification toggles.

## Technologies Used

*   React
*   JavaScript
*   Context API
*   Tailwind CSS (for styling)

## Architecture or Code Overview

The component is structured with the following key elements:

*   **State Management:**
    *   `activeTab`: Tracks the currently active tab ('profile' or 'preferences').
    *   `isEditing`:  Indicates whether the profile information is in edit mode.
    *   `profileData`: Stores user profile information, initialized from the `currentUser` from the `dataContext`.
    *   `preferences`: Stores notification preference settings (e.g., email, SMS, push).
*   **Context API:**
    *   Uses `dataContext` to access the `currentUser` object.
*   **Conditional Rendering:**
    *   `renderTabContent()` renders the appropriate tab content based on `activeTab`.
*   **Profile Tab:**
    *   Allows editing of profile information (first name, last name, email, phone, address).
    *   Uses a form with input fields that are disabled when not in edit mode.
    *   Provides "Edit Profile", "Cancel", and "Save Changes" buttons.
*   **Preferences Tab:**
    *   Displays toggle switches for different notification settings.
*   **Event Handlers:**
    *   `setActiveTab()`: Changes the active tab.
    *   `handleProfileSave()`: Saves profile changes (currently displays an alert).
    *   `handleToggle()`: Toggles the state of a specific preference.
    *   `handleChange()`: Handles changes to profile input fields.

## How to Use

1.  **Installation:**

    *   Ensure all dependencies of the parent project are installed (e.g., using `npm install` or `yarn install`).
    *   Ensure that the `dataContext` is correctly set up.
2.  **Usage:**
    *   Import and render the `Settings` component within your application.
    *   The component will display the settings interface, including profile information and preferences.
    *   The `currentUser` object from `dataContext` should provide the initial profile data.

## Known Issues / Improvements

*   **Profile Saving:** The `handleProfileSave` function currently only displays an alert; implement actual data saving (e.g., API calls).
*   **Data Persistence:** Profile changes are not persisted. Implement backend integration to store and retrieve user settings.
*   **Error Handling:** Add error handling (e.g., for API calls) and user feedback.
*   **Validation:** Implement input validation for profile fields.

## Additional Notes or References

This component is part of a larger application, potentially related to the "Crime Master" project (as indicated in the existing `README` information).  It relies on the `dataContext` for user data.