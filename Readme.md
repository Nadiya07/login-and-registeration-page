markdown
Copy code
# Secrets App

Secrets App is a simple web application built using Express.js, PostgreSQL, and EJS. It allows users to register and log in to view secret content.

## Features

- User registration with email and password
- User login with email and password
- Stores user data in a PostgreSQL database
- Renders HTML views using EJS templates

## Prerequisites

- Node.js
- PostgreSQL

## Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/secrets-app.git
   cd secrets-app
Install dependencies:

bash
Copy code
npm install
Set up PostgreSQL:

Create a PostgreSQL database named secrets.
Create a table named users with the following schema:
sql
Copy code
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  email VARCHAR(255) UNIQUE NOT NULL,
  password VARCHAR(255) NOT NULL
);
Configure the database connection:

Update the PostgreSQL connection settings in app.js:
javascript
Copy code
const db = new pg.Client({
  user: "postgres",
  host: "localhost",
  database: "secrets",
  password: "your-password",
  port: 5432,
});
Running the App
Start the server:

bash
Copy code
npm start
Open your browser and navigate to:

arduino
Copy code
http://localhost:3000
Folder Structure
csharp
Copy code
secrets-app/
├── public/                 # Static files (CSS, images)
├── views/                  # EJS templates
│   ├── home.ejs
│   ├── login.ejs
│   └── register.ejs
├── app.js                  # Main application file
├── package.json            # NPM dependencies and scripts
└── README.md               # This file
Routes
GET / - Renders the home page
GET /login - Renders the login page
GET /register - Renders the registration page
POST /register - Handles user registration
POST /login - Handles user login
Troubleshooting
"User not found" Error
If you encounter a "User not found" error when trying to log in, ensure the following:

The email address is correctly converted to lowercase both during registration and login.
The form field names in your HTML match the ones expected in the Express code.
The PostgreSQL connection is properly established and the users table exists.
Debugging
Add the following debugging lines in your app.js to help identify issues:

javascript
Copy code
console.log(`Email: ${email}, Password: ${password}`); // Debugging line
console.log(result.rows); // Debugging line