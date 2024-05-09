# SDEV-255-M07-Tutorial-Bringing-It-All-Together

This project is a web application for student and teacher interaction. It allows teachers to create, update, and destroy courses, while students can add and remove courses to a shopping cart.

## Technology Stack

- Frontend: HTML, JavaScript, Tailwind CSS
- Backend: Node.js with Express, MongoDB

## Authorization and Authentication

For user authorization, the project follows these steps:

1. **Login**: Before the client sends the username and password to the server, bcrypt encrypts the password. The server then checks the database to see if the login and password are correct. If correct, the server creates a token with JWT with an expiration, then puts it in the client's cookie.

2. **Access Tokens**: To send access tokens from front to back or back to front, cookies are used. For login or signup, where you have to send the username and password from front to back, fetch post could be replaced with a form submission method.

3. **Session Management**: The project includes a session countdown timer that will auto logout based on setInterval subtracting every second. expiresIn is based on the date when the token is created + time given minus now. If the token expires, when the user navigates to a new route, the server will know the token is expired and direct the user to logout.

## Deployment

To deploy to Firebase, you can follow the instructions [here](https://cloud.google.com/build/docs/deploying-builds/deploy-firebase). If you encounter issues, consider trying App Engine instead. app.yaml is used to deploy from VS Code to App Engine. Environment variables can be set using this approach.

## Workflow

The suggested workflow is to push to GitHub, and App Engine should auto-deploy the changes.

For more details, you can refer to the [video tutorial series](https://www.youtube.com/watch?v=HgpCjChgjoQ&list=PL42xwJRIG3xCtmOrJAQFR5sIJFKIJ9MEn&index=2).
