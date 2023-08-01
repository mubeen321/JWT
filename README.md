Project README
Description
This is a simple Express application that provides user registration, login, and a protected route using JSON Web Tokens for authentication. It utilizes MongoDB as the database to store user information.

Requirements
Node.js and npm installed on your machine
MongoDB database
Installation
Clone the repository to your local machine:

bash
Copy code
git clone <repository_url>
Navigate to the project directory:

bash
Copy code
cd <project_directory>
Install the required dependencies:

Copy code
npm install
Create a .env file in the root directory and set the following environment variables:

makefile
Copy code
TOKEN_KEY=<your_secret_token_key>
MONGO_URI=<your_mongodb_connection_uri>
Replace <your_secret_token_key> with a secret key of your choice for signing JWT tokens. Also, provide the connection URI for your MongoDB database as <your_mongodb_connection_uri>.

Running the Application
To start the server, run the following command:

sql
Copy code
npm start
The application will be running on http://localhost:3000.

Endpoints
POST /register: Register a new user with the following JSON data in the request body:

perl
Copy code
{
"first_name": "John",
"last_name": "Doe",
"email": "johndoe@example.com",
"password": "password123"
}
If successful, the API will respond with the newly created user object and a JWT token.

POST /login: Login with an existing user using the following JSON data in the request body:

perl
Copy code
{
"email": "johndoe@example.com",
"password": "password123"
}
If the login is successful, the API will respond with the user object and a new JWT token.

GET /welcome: A protected route that requires a valid JWT token. Include the token in the Authorization header with the value Bearer <token> to access this route. For example:

makefile
Copy code
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
If the token is valid, the API will respond with "Welcome 🙌".

Models
User: Represents the user schema in the MongoDB database. It includes fields for first name, last name, email, and the encrypted password.
Middleware
auth: Middleware to protect routes from unauthorized access. It verifies the JWT token in the Authorization header and adds the authenticated user to the req.user object.
Error Handling
If a route that is not defined is accessed, the API will respond with a 404 status code and a JSON object containing the error message.
Contributions
Contributions to this project are welcome! Feel free to submit pull requests or open issues for any improvements or bug fixes.

Contact
If you have any questions or need further assistance, you can reach out to the project maintainers at chughtaimubeen5@gmail.com.
