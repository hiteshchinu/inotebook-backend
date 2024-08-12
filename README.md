# iNotebook Backend

This is the backend for the iNotebook application, a platform to manage notes securely with authentication and CRUD operations. It is built using Node.js, Express, MongoDB, and Mongoose.

## Features

- **User Authentication**: Secure user registration and login using JWT.
- **Notes Management**: Add, update, delete, and fetch notes with user-specific authorization.
- **Data Validation**: Validate user input for authentication and note operations using `express-validator`.
- **Secure Password Storage**: Passwords are hashed using `bcryptjs` for security.
- **Middleware**: Custom middleware to fetch authenticated users.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/hiteshchinu/inotebook-backend.git
   cd inotebook-backend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Setup MongoDB:
   - Ensure MongoDB is running on your machine.
   - The app is configured to connect to `mongodb://localhost:27017` by default. Update the `mongoURI` in `db.js` if necessary.

4. Set up environment variables:
   - Create a `.env` file in the root directory and add the following:
     ```
     JWT_SECRET=your_jwt_secret_key
     ```

## Running the Server

Start the development server using `nodemon`:
```bash
nodemon .\index.js
```

The server will be running at `http://localhost:5000`.

## API Endpoints

### Authentication

- **POST** `/api/auth/createuser`  
  Create a new user.

- **POST** `/api/auth/login`  
  Authenticate a user and get a token.

- **POST** `/api/auth/getuser`  
  Get the logged-in user's details.

### Notes

- **GET** `/api/notes/fetchallnotes`  
  Fetch all notes for the logged-in user.

- **POST** `/api/notes/addnote`  
  Add a new note for the logged-in user.

- **PUT** `/api/notes/updatenote/:id`  
  Update an existing note for the logged-in user.

- **DELETE** `/api/notes/deletenote/:id`  
  Delete an existing note for the logged-in user.

## Middleware

- **fetchuser**  
  Middleware to authenticate users based on JWT tokens.


## Contributing

Feel free to fork this repository and submit pull requests. Any contributions are welcome!
