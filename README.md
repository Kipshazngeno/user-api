# User Management API

## Setup

1. Clone the repository:
   git clone <repository-url>
   cd user-api

2. Install dependencies:
   npm install

3. Start the server:
   node index.js

4. API will be available at http://localhost:3000

## API Endpoints

### Get All Users
- URL: /api/users
- Method: GET
- Success Response:
  - Code: 200
  - Content:
    [
      { "id": 1, "name": "John", "email": "john@example.com" },
      { "id": 2, "name": "Jane", "email": "jane@example.com" }
    ]

### Get User by ID
- URL: /api/users/:id
- Method: GET
- URL Params: id=[integer]
- Success Response:
  - Code: 200
  - Content:
    { "id": 1, "name": "John", "email": "john@example.com" }
- Error Response:
  - Code: 404
  - Content:
    { "message": "User not found" }

### Create User
- URL: /api/users
- Method: POST
- Body:
  {
    "name": "Alice",
    "email": "alice@example.com"
  }
- Success Response:
  - Code: 201
  - Content:
    { "id": 3, "name": "Alice", "email": "alice@example.com" }
- Error Response:
  - Code: 400
  - Content:
    { "message": "Name and email are required" }

### Update User
- URL: /api/users/:id
- Method: PUT
- URL Params: id=[integer]
- Body:
  {
    "name": "Alice Updated",
    "email": "alice_updated@example.com"
  }
- Success Response:
  - Code: 200
  - Content:
    { "id": 3, "name": "Alice Updated", "email": "alice_updated@example.com" }
- Error Response:
  - Code: 404
  - Content:
    { "message": "User not found" }
  - Code: 400
  - Content:
    { "message": "Name and email are required" }

### Delete User
- URL: /api/users/:id
- Method: DELETE
- URL Params: id=[integer]
- Success Response:
  - Code: 204
- Error Response:
  - Code: 404
  - Content:
    { "message": "User not found" }

## Error Handling
- Validation errors (e.g., missing required fields like "name" or "email") return a 400 status code with a message like:
  { "message": "Name and email are required" }
- Resource not found errors (e.g., a user with a specific ID doesn't exist) return a 404 status code with a message like:
  { "message": "User not found" }

## License
This project is licensed under the MIT License.
