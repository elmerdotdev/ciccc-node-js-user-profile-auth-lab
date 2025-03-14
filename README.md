# NodeJS - User Profile with Authentication

**Goal:** Create a mini user profile system using Node.js and Express (MVC pattern) for the backend and Astro for the frontend/view.

## Instructions

1. Create a directory called `frontend` in the root of your project. Inside the directory, install Astro.
2. Install the necessary packages and files you will need for the `backend`. Some of the starter files have also been added in.
3. Create your server, routes, controllers, and models inside your backend. You have full control over your backend so feel free to add or create your own functions/methods if necessary:
  
    **Model (`src/models/user.model.ts`)**

    *Fields:*
    - id (string uuid)
    - username (string)
    - password (string hashed)
    - firstname (string)
    - lastname (string)

    *Methods*
    - findAll()
    - findById(id)
    - findByUsername(username)
    - login(username, password)
    - create()
    - update(id)
    - delete(id)

    ---

    **Controller (`src/controllers/user.controller.ts`)**
    - getUsers()
    - getUserById(id)
    - getUserByUsername(username)
    - loginUser()
    - addUser()
    - updateUserById(id)
    - deleteUserById(id)
    - logout()

    ---

    **Routes (`src/routes/user.routes.ts`)**
    - `POST /signup` = add user
    - `POST /login` = check if username exist, return cookie/s username
    - `GET /logout` = clear the cookies
    - `GET /check-auth` = check auth cookie/s
    - `GET /users` = get all users
    - `GET /user/:id` = get user by id
    - `PUT /user/:id` = update user by id
    - `DELETE /user/:id` = delete user by id

4. Make sure that you set up your CORS middleware on your `server.ts` so that your frontend can communicate with your backend.

    ```js
    app.use(cors({
      origin: 'http://localhost:4321', // Astro port
      credentials: true // allow cookies
    }))
    app.use(express.json())
    app.use(express.urlencoded({ extended: true }))
    ```

5. Test your backend routes using [Postman](https://www.postman.com/) or similar software to verify that everything is working correctly.
6. On your Astro frontend, create 3 pages:
    - Login (`/login`): Login form with username and password.
    - Register (`/register`): Signup form with username, password, firstname, and lastname fields.
    - Profile (`/profile`): A protected page that should only display information if the user is authenticated or logged in.
7. When a user successfully logs in, they should be redirected to the profile page. The profile page should just display user data and a logout button. Due to time-constraints, no need to build edit and delete functionalities:
    - Username
    - First name
    - Last name
    - Logout button
8. Clicking on the logout button will send a request to the backend `/logout` route and then on the frontend, redirect the user to the login page.
9. Commit and push your changes once you are done.

Good luck! 🎉🎉🎉
