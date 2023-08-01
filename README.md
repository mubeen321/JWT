<!DOCTYPE html>
<html>
<head>
  <title>Project Name</title>
</head>
<body>
  <h1 style="text-align: center; color: #336699;">Project Name</h1>

  <p style="text-align: center;">
    <img src="https://img.shields.io/badge/build-passing-brightgreen" alt="Build Status">
    <img src="https://img.shields.io/badge/coverage-90%25-brightgreen" alt="Code Coverage">
  </p>

  <p style="text-align: center;">
    <img src="https://user-images.githubusercontent.com/12345678/screenshot.png" alt="Project Screenshot" width="500">
  </p>

  <h2>Description</h2>

  <p>
    This is a fancy Express application that provides user registration, login, and a protected route using JSON Web Tokens for authentication. It utilizes MongoDB as the database to store user information.
  </p>

  <h2>Requirements</h2>

  <ul>
    <li>Node.js and npm installed on your machine</li>
    <li>MongoDB database</li>
  </ul>

  <h2>Installation</h2>

  <ol>
    <li>Clone the repository to your local machine:</li>
  </ol>
  <pre><code>git clone &lt;repository_url&gt;</code></pre>

  <ol start="2">
    <li>Navigate to the project directory:</li>
  </ol>
  <pre><code>cd &lt;project_directory&gt;</code></pre>

  <ol start="3">
    <li>Install the required dependencies:</li>
  </ol>
  <pre><code>npm install</code></pre>

  <ol start="4">
    <li>Create a <code>.env</code> file in the root directory and set the following environment variables:</li>
  </ol>
  <pre>
<code>TOKEN_KEY=&lt;your_secret_token_key&gt;
MONGO_URI=&lt;your_mongodb_connection_uri&gt;</code></pre>

  <p>
    Replace <code>&lt;your_secret_token_key&gt;</code> with a secret key of your choice for signing JWT tokens. Also, provide the connection URI for your MongoDB database as <code>&lt;your_mongodb_connection_uri&gt;</code>.
  </p>

  <h2>Running the Application</h2>

  <p>
    To start the server, run the following command:
  </p>
  <pre><code>npm start</code></pre>

  <p>
    The application will be running on <a href="http://localhost:3000">http://localhost:3000</a>.
  </p>

  <h2>Endpoints</h2>

  <ol>
    <li><strong>POST /register:</strong> Register a new user with the following JSON data in the request body:</li>
  </ol>
  <pre><code>{
  "first_name": "John",
  "last_name": "Doe",
  "email": "johndoe@example.com",
  "password": "password123"
}</code></pre>

  <p>
    If successful, the API will respond with the newly created user object and a JWT token.
  </p>

  <ol start="2">
    <li><strong>POST /login:</strong> Login with an existing user using the following JSON data in the request body:</li>
  </ol>
  <pre><code>{
  "email": "johndoe@example.com",
  "password": "password123"
}</code></pre>

  <p>
    If the login is successful, the API will respond with the user object and a new JWT token.
  </p>

  <ol start="3">
    <li><strong>GET /welcome:</strong> A protected route that requires a valid JWT token. Include the token in the <code>Authorization</code> header with the value <code>Bearer &lt;token&gt;</code> to access this route. For example:</li>
  </ol>
  <pre>
<code>Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...</code></pre>

  <p>
    If the token is valid, the API will respond with "Welcome 🙌".
  </p>

  <h2>Models</h2>

  <ol>
    <li><strong>User:</strong> Represents the user schema in the MongoDB database. It includes fields for first name, last name, email, and the encrypted password.</li>
  </ol>

  <h2>Middleware</h2>

  <ol>
    <li><strong>auth:</strong> Middleware to protect routes from unauthorized access. It verifies the JWT token in the <code>Authorization</code> header and adds the authenticated user to the <code>req.user</code> object.</li>
  </ol>

  <h2>Error Handling</h2>

  <p>
    If a route that is not defined is accessed, the API will respond with a 404 status code and a JSON object containing the error message.
  </p>

  <h2>Contributions</h2>

  <p>
    Contributions to this project are welcome! Feel free to submit pull requests or open issues for any improvements or bug fixes.
  </p>

  <h2>Contact</h2>

  <p>
    If you have any questions or need further assistance, you can reach out to the project maintainers at <a href="mailto:chughtaimubeen5@gmail.com">chughtaimubeen5@gmail.com</a>.
  </p>
</body>
</html>
