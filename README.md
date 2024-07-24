# Express and Socket.IO Server

This project sets up an Express server integrated with Socket.IO to handle real-time communication, authentication using JWT, and cookie-based session management. The server allows cross-origin requests and provides basic routing for login and message functionalities.

## Features

- **Express Server**: Serves HTTP requests.
- **Socket.IO**: Enables real-time bidirectional communication.
- **JWT Authentication**: Provides authentication using JSON Web Tokens.
- **CORS**: Supports cross-origin requests from a specific origin.
- **Cookie Parser**: Parses cookies for authentication.

## Installation

1. **Clone the repository**:
    ```bash
    git clone <https://github.com/deltaTH/web-sockets.git>
    cd <repository_directory>
    ```

2. **Install dependencies**:
    ```bash
    npm install
    ```

## Usage

1. **Start the server**:
    ```bash
    npm start
    ```

2. **Access the application**:
    Open your web browser and go to `http://localhost:3000`.

## Endpoints

- **GET /**: Returns a "Hello World!" message.
- **GET /login**: Generates a JWT token and sets it as an HTTP-only, secure cookie. Responds with a JSON message indicating a successful login.

## Socket.IO Events

- **connection**: Logs when a user connects.
- **message**: Listens for messages from a client and emits them to a specific room.
- **join-room**: Joins a client to a specific room.
- **disconnect**: Logs when a user disconnects.

## Configuration

- **Port**: The server runs on port `3000` by default. You can change this by modifying the `port` variable.
- **CORS**: The server is configured to accept requests from `http://localhost:5173`. Update this in the `cors` configuration if your frontend is hosted elsewhere.
- **JWT Secret Key**: The secret key for JWT is set to `asdasdsadasdasdasdsa`. Change this to a secure key in a production environment.

## Middleware

- **CORS**: Configured to allow requests from `http://localhost:5173` with GET and POST methods.
- **Cookie Parser**: Parses cookies for incoming requests.
- **JWT Verification**: Middleware to verify JWT tokens for Socket.IO connections.

## Example Requests

1. **Login Request**:
    ```bash
    curl -X GET http://localhost:3000/login
    ```

2. **WebSocket Connection**:
    ```javascript
    const socket = io('http://localhost:3000', { withCredentials: true });
    ```

3. **Join Room**:
    ```javascript
    socket.emit('join-room', 'room1');
    ```

4. **Send Message**:
    ```javascript
    socket.emit('message', { room: 'room1', message: 'Hello Room1!' });
    ```

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Acknowledgments

- [Express](https://expressjs.com/)
- [Socket.IO](https://socket.io/)
- [jsonwebtoken](https://www.npmjs.com/package/jsonwebtoken)
- [cors](https://www.npmjs.com/package/cors)
- [cookie-parser](https://www.npmjs.com/package/cookie-parser)

---
