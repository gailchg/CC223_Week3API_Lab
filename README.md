# CC223 Week 3 API Lab
# Coching, Gladys Gail S.
# BSIT - 2A
# Applications Development and Emerging Technologies

This project is a simple API demonstrating user authentication with JWT, RESTful API endpoints, and basic security measures.

## Setup Instructions

### Prerequisites
Make sure you have the following installed:
- [Node.js](https://nodejs.org/en/download/)
- [Postman](https://www.postman.com/downloads/) (optional, for testing API)

### Installation
1. Clone the repository:
   ```sh
   git clone https://github.com/gailchg/CC223_Week3API_Lab.git
   cd CC223_Week3API_Lab
   ```
2. Install dependencies:
   ```sh
   npm install
   ```
3. Create a `.env` file and add your secret key:
   ```env
   SECRET_KEY=your_secret_key
   PORT=5000
   ```
4. Start the server:
   ```sh
   node server.js
   ```

## API Endpoints

### 1️. User Registration
**Endpoint:** `POST /api/register`
- **Description:** Registers a new user.
- **Request Body:**
  ```json
  {
    "username": "testuser",
    "password": "password123"
  }
  ```
- **Response:**
  ```json
  {
    "message": "User registered successfully"
  }
  ```

### 2. User Login
**Endpoint:** `POST /api/login`
- **Description:** Logs in a user and returns a JWT.
- **Request Body:**
  ```json
  {
    "username": "testuser",
    "password": "password123"
  }
  ```
- **Response:**
  ```json
  {
    "token": "your_jwt_token"
  }
  ```

### 3. Protected Route (Requires Authentication)
**Endpoint:** `GET /api/protected`
- **Description:** Returns a welcome message if the user is authenticated.
- **Headers:**
  ```
  Authorization: Bearer <your_jwt_token>
  ```
- **Response:**
  ```json
  {
    "message": "Hello, testuser! Welcome to the protected route."
  }
  ```

## 📌 Example Usage
You can test the API using **Postman** or **cURL**:
```sh
curl -X POST -H "Content-Type: application/json" -d '{"username":"testuser","password":"password123"}' http://localhost:5000/api/login
```

## 📝 Notes
- The API uses **JWT for authentication**.
- Ensure your `.env` file contains a valid `SECRET_KEY`.
- Start the server before making requests.
