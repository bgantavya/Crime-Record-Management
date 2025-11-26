# Crime Master - User Model

**Folder Structure**

```
📂 [root]
└── 📄 user.model.js
```

**Description**

This project defines the User model for the Crime Master application. It uses Mongoose to create a schema and model for user data, including fields for first name, last name, username, email, password, and role.

**How to Use**

This model is intended to be used within a MERN (MongoDB, Express.js, React, Node.js) stack.

1.  **Installation:**

    Ensure you have Node.js and npm/yarn installed.

    Install dependencies: `npm install mongoose` or `yarn add mongoose`
2.  **Usage Example:**

    ```javascript
    import User from './user.model.js';

    // Example: Create a new user
    const newUser = new User({
        firstname: 'John',
        lastname: 'Doe',
        username: 'johndoe',
        email: 'john.doe@example.com',
        password: 'password123'
    });

    newUser.save()
        .then(user => console.log('User saved:', user))
        .catch(err => console.error('Error saving user:', err));
    ```

**Technologies Used**

*   JavaScript (ES6+)
*   Node.js
*   Mongoose
*   MongoDB (database)

**Architecture or Code Overview**

*   `userSchema`: Defines the structure of the user document with fields like `firstname`, `lastname`, `username`, `email`, `password`, and `role`. The schema includes validation such as `required` and `unique`.
*   `User`: The Mongoose model created from the `userSchema`. This model is used to interact with the "User" collection in the MongoDB database. The `timestamps:true` option automatically adds `createdAt` and `updatedAt` fields.

**Known Issues / Improvements**

*   **Password Security:** The current implementation doesn't include password hashing (e.g., using bcrypt). This should be implemented for production use.
*   **Validation:**  More robust validation could be added to the schema (e.g., email format validation, password strength checks).
*   **Error Handling:** Implement more comprehensive error handling.

**Additional Notes or References**

*   This model is a core component of the Crime Master application.
*   This uses Mongoose, an Object-Document Mapper (ODM) for MongoDB.