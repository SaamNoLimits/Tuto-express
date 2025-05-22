# Express.js User Management API

A simple REST API built with Express.js for managing users. This project demonstrates basic CRUD operations with an in-memory database.

## Features

- ✅ Create, Read, Update, and Delete users
- ✅ RESTful API endpoints
- ✅ JSON request/response handling
- ✅ Input validation
- ✅ Error handling middleware
- ✅ In-memory data storage

## Prerequisites

Before running this application, make sure you have the following installed:

- [Node.js](https://nodejs.org/) (version 14 or higher)
- [npm](https://www.npmjs.com/) (comes with Node.js)

## Installation

1. Clone the repository:
```bash
git clone <your-repository-url>
cd <project-directory>
```

2. Install dependencies:
```bash
npm install express body-parser
```

## Usage

1. Start the server:
```bash
node app.js
```

2. The server will start on port 3000 (or the port specified in the PORT environment variable).

3. You should see the message: `Server started on port 3000`

## API Endpoints

### Base URL
```
http://localhost:3000
```

### Endpoints

| Method | Endpoint | Description | Request Body |
|--------|----------|-------------|--------------|
| GET | `/` | Welcome message | - |
| GET | `/api/users` | Get all users | - |
| GET | `/api/users/:id` | Get user by ID | - |
| POST | `/api/users` | Create new user | `{ "name": "string", "email": "string" }` |
| PUT | `/api/users/:id` | Update user | `{ "name": "string", "email": "string" }` |
| DELETE | `/api/users/:id` | Delete user | - |

## API Examples

### Get all users
```bash
curl -X GET http://localhost:3000/api/users
```

### Get single user
```bash
curl -X GET http://localhost:3000/api/users/1
```

### Create a new user
```bash
curl -X POST http://localhost:3000/api/users \
  -H "Content-Type: application/json" \
  -d '{"name": "John Doe", "email": "john@example.com"}'
```

### Update a user
```bash
curl -X PUT http://localhost:3000/api/users/1 \
  -H "Content-Type: application/json" \
  -d '{"name": "Updated Name", "email": "updated@example.com"}'
```

### Delete a user
```bash
curl -X DELETE http://localhost:3000/api/users/1
```

## Sample Data

The API comes with pre-loaded sample data:

```json
[
  {
    "id": 1,
    "name": "Oussama AHJLI",
    "email": "Oussama@mancity.uk"
  },
  {
    "id": 2,
    "name": "Kevin de bruyne",
    "email": "kdb@mancity.uk"
  }
]
```

## Response Format

### Success Response
```json
{
  "id": 1,
  "name": "User Name",
  "email": "user@example.com"
}
```

### Error Response
```json
{
  "message": "Error description"
}
```

### HTTP Status Codes

- `200` - OK (successful GET, PUT)
- `201` - Created (successful POST)
- `400` - Bad Request (validation errors)
- `404` - Not Found (user doesn't exist)
- `500` - Internal Server Error

## Project Structure

```
project-root/
│
├── app.js          # Main application file
├── package.json    # Project dependencies and scripts
└── README.md       # Project documentation
```

## Dependencies

- **express**: Fast, unopinionated, minimalist web framework for Node.js
- **body-parser**: Node.js body parsing middleware

## Development

### Running in Development Mode

For development with auto-restart on file changes, you can use nodemon:

```bash
npm install -g nodemon
nodemon app.js
```

### Testing the API

You can test the API using:
- [Postman](https://www.postman.com/)
- [Insomnia](https://insomnia.rest/)
- curl commands (as shown in examples above)
- Any HTTP client

## Environment Variables

- `PORT`: Server port (default: 3000)

Example:
```bash
PORT=8080 node app.js
```

## Limitations

- Uses in-memory storage (data is lost when server restarts)
- No authentication or authorization
- No data persistence
- Basic validation only

## Future Enhancements

- [ ] Add database integration (MongoDB, PostgreSQL, etc.)
- [ ] Implement user authentication
- [ ] Add data validation with schemas
- [ ] Add logging middleware
- [ ] Add unit tests
- [ ] Add API documentation with Swagger
- [ ] Add rate limiting
- [ ] Add CORS support

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is open source and available under the [MIT License](LICENSE).

## Author

Created with ❤️ by Oussama AHJLI

---
Note: This is a basic API for learning purposes. For production use, consider implementing proper database integration, authentication, and security measures.
