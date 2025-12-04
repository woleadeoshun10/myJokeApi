#  😂 My Joke API

A RESTful API built with Node.js and Express for managing and retrieving jokes. This project demonstrates full CRUD operations, authentication, and filtering capabilities.

**Author:** Adewole Adeoshun

## Features

-  Get random jokes
-  Retrieve specific jokes by ID
-  Filter jokes by type/category
-  Create new jokes
-  Update existing jokes (PUT/PATCH)
-  Delete jokes individually or all at once
-  API key authentication for sensitive operations
-  100 pre-loaded jokes across multiple categories

## Tech Stack

- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **Body-Parser** - Request body parsing middleware

## Getting Started

### Prerequisites

- Node.js (v14 or higher)
- npm or yarn

### Installation

1. Clone the repository:

```bash
git clone https://github.com/woleadeoshun10/myOwnApi.git

```

1. Install dependencies:

```bash
npm install express
npm install body-parser
npm install express
```

1. Start the server:

```bash
node index.js

OR

npm run server
```

The server will run on `http://localhost:3000`

## API Endpoints

### 1. Get Random Joke

```
GET /random
```

Returns a random joke from the collection.

**Response:**

```json
{
  "id": 5,
  "jokeText": "Why do we never tell secrets on a farm?...",
  "jokeType": "Wordplay"
}
```

-----

### 2. Get Specific Joke

```
GET /jokes/:id
```

Returns a joke with the specified ID.

**Example:**

```
GET /jokes/2
```

**Response:**

```json
{
  "id": 2,
  "jokeText": "Why did the scarecrow win an award?...",
  "jokeType": "Puns"
}
```

-----

### 3. Filter Jokes by Type

```
GET /filter?type={jokeType}
```

Returns all jokes matching the specified type.

**Example:**

```
GET /filter?type=Science
```

**Available Types:** Science, Puns, Wordplay, Math, Food, Sports, Movies

**Response:**

```json
[
  {
    "id": 1,
    "jokeText": "Why don't scientists trust atoms?...",
    "jokeType": "Science"
  },
  {
    "id": 6,
    "jokeText": "How do you organize a space party?...",
    "jokeType": "Science"
  }
]
```

-----

### 4. Create New Joke

```
POST /jokes
Content-Type: application/json
```

**Request Body:**

```json
{
  "text": "Why did the bicycle fall over? It was two tired!",
  "type": "Puns"
}
```

**Response:**

```json
{
  "id": 101,
  "jokeText": "Why did the bicycle fall over? It was two tired!",
  "jokeType": "Puns"
}
```

-----

### 5. Replace Joke (PUT)

```
PUT /jokes/:id
Content-Type: application/json
```

Completely replaces the joke at the specified ID.

**Request Body:**

```json
{
  "text": "Updated joke text",
  "type": "Wordplay"
}
```

-----

### 6. Update Joke (PATCH)

```
PATCH /jokes/:id
Content-Type: application/json
```

Partially updates a joke - only include fields you want to change.

**Request Body:**

```json
{
  "type": "Science"
}
```

-----

### 7. Delete Specific Joke

```
DELETE /jokes/:id
```

**Example:**

```
DELETE /jokes/5
```

**Success Response:** `200 OK`

**Error Response:** `404 Not Found`

-----

### 8. Delete All Jokes (Authenticated)

```
DELETE /all?key={masterKey}
```

Requires API key authentication to delete all jokes.

**Example:**

```
DELETE /all?key=25771f9f-bb03-4548-ac23-650fde0cb0c4
```

**Success Response:** `200 OK`

**Unauthorized Response:** `404 Not Found`

## Testing the API

### Using cURL

**Get random joke:**

```bash
curl http://localhost:3000/random
```

**Create new joke:**

```bash
curl -X POST http://localhost:3000/jokes \
  -H "Content-Type: application/json" \
  -d '{"text": "Your joke here", "type": "Puns"}'
```

**Filter jokes:**

```bash
curl http://localhost:3000/filter?type=Science
```

### Using Postman

1. Import the endpoints listed above
2. Set method (GET, POST, PUT, PATCH, DELETE)
3. Add request body for POST/PUT/PATCH operations
4. Send request and view response

## Project Structure

```
joke-api/
├── index.js          # Main application file with routes and logic
├── package.json      # Project dependencies and scripts
└── README.md         # This file
```

## Future Enhancements

- [ ] Add database integration (MongoDB/PostgreSQL)
- [ ] Implement user authentication with JWT
- [ ] Add pagination for large result sets
- [ ] Create joke ratings/voting system
- [ ] Add search functionality
- [ ] Implement rate limiting
- [ ] Add input validation and sanitization
- [ ] Deploy to cloud platform (Heroku/Railway/Render)

## API Design Principles Used

- **RESTful conventions** - Standard HTTP methods for CRUD operations
- **Proper status codes** - 200, 201, 404, etc.
- **JSON responses** - Consistent data format
- **Query parameters** - For filtering and authentication
- **Path parameters** - For resource identification
- **Error handling** - Meaningful error messages

## Learning Outcomes

This project demonstrates:

- Building REST APIs with Express.js
- CRUD operations (Create, Read, Update, Delete)
- HTTP methods (GET, POST, PUT, PATCH, DELETE)
- Middleware usage (body-parser)
- Route parameters and query strings
- Basic authentication with API keys
- Array manipulation methods (find, filter, findIndex, splice)

## License

This project is open source and available for educational purposes.

## Contact

**Adewole Adeoshun**

- GitHub: [@woleadeoshun10](https://github.com/woleadeoshun10)
- Email: woleadeoshun18@gmail.com

-----
