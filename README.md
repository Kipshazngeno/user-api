# User Management API

## Setup
1. Clone the repository
2. Run `npm install`
3. Start the server: `node index.js`
4. API will be available at `http://localhost:3000`

## API Endpoints

### Get User by ID
- **URL**: `/api/users/:id`
- **Method**: `GET`
- **URL Params**: `id=[integer]`
- **Success Response**: 
  - Code: 200
  - Content: `{ id: 1, name: "John", email: "john@example.com" }`
- **Error Response**:
  - Code: 404
  - Content: `{ message: "User not found" }`

### Get All Users
- **URL**: `/api/users`
- **Method**: `GET`
- **Success Response**: 
  - Code: 200
  - Content: `[{ id: 1, name: "John", email: "john@example.com" }, { id: 2, name: "Jane", email: "jane@example.com" }]`
  
### Create a New User
- **URL**: `/api/users`
- **Method**: `POST`
- **Data Params**: 
  - `{ "name": "John", "email": "john@example.com" }`
- **Success Response**: 
  - Code: 201
  - Content: `{ id: 3, name: "John", email: "john@example.com" }`
- **Error Response**:
  - Code: 400
  - Content: `{ message: "Invalid input data" }`

### Update User
- **URL**: `/api/users/:id`
- **Method**: `PUT`
- **URL Params**: `id=[integer]`
- **Data Params**: 
  - `{ "name": "Updated Name", "email": "updated@example.com" }`
- **Success Response**: 
  - Code: 200
  - Content: `{ id: 1, name: "Updated Name", email: "updated@example.com" }`
- **Error Response**:
  - Code: 404
  - Content: `{ message: "User not found" }`

### Delete User
- **URL**: `/api/users/:id`
- **Method**: `DELETE`
- **URL Params**: `id=[integer]`
- **Success Response**: 
  - Code: 200
  - Content: `{ message: "User deleted successfully" }`
- **Error Response**:
  - Code: 404
  - Content: `{ message: "User not found" }`

## Error Handling
- **404**: When the requested resource is not found.
- **400**: When the input data is invalid.
- **500**: Internal server errors.

