# Go Movies CRUD Backend 🎬

A simple RESTful Movies API built with Go and Gorilla Mux. Offers full CRUD (Create, Read, Update, Delete) operations on an in-memory collection of movies, each with an ID, ISBN, title, and director (first/last name). Ideal for learning how to build APIs in Go.

## Table of Contents
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Running the Server](#running-the-server)
- [API Endpoints](#api-endpoints)
- [Project Structure](#project-structure)
- [Usage Examples](#usage-examples)
- [Error Handling](#error-handling)
- [Contributing](#contributing)
- [License](#license)

---

## Features
- In-memory data store (no external database required)
- RESTful HTTP endpoints using Gorilla Mux
- JSON request and response handling
- Auto-generated movie IDs
- Beginner-friendly structure

---

## Prerequisites
- Go installed (version 1.16+ recommended)
- Properly set up `GOPATH` and Go environment variables

---

## Installation
- clone this repository
- install dependencies:
```
# Clone the repo
cd go-movies-crud-backend

# Install dependencies
go mod tidy
```

---

## Running the Server

```
# Run directly
go run main.go

# Or build and run
go build -o movies-backend .
./movies-backend
```

Server will start on `http://localhost:8000`

---

## API Endpoints

| Method | Endpoint         | Description              | Body (JSON) |
|--------|------------------|--------------------------|-------------|
| GET    | `/movies`        | List all movies          | –           |
| GET    | `/movies/{id}`   | Retrieve one movie       | –           |
| POST   | `/movies`        | Create a new movie       | `{ "isbn": "...", "title": "...", "director": { "firstname": "...", "lastname": "..." } }` |
| PUT    | `/movies/{id}`   | Update an existing movie | Same as POST body |
| DELETE | `/movies/{id}`   | Delete a movie           | –           |

### Example JSON

```
{
  "id": "1",
  "isbn": "448743",
  "title": "Movie Title",
  "director": {
    "firstname": "John",
    "lastname": "Doe"
  }
}
```

---

## Project Structure

```
.
├── main.go        # API server with models and handlers
└── go.mod         # Go module file
```

---

## Usage Examples

```
# Get all movies
curl http://localhost:8000/movies

# Add a movie
curl -X POST -d '{"isbn":"12345","title":"New Movie","director":{"firstname":"Jane","lastname":"Roe"}}' \
  -H "Content-Type: application/json" http://localhost:8000/movies

# Update a movie
curl -X PUT -d '{"isbn":"54321","title":"Updated Title","director":{"firstname":"Jane","lastname":"Doe"}}' \
  -H "Content-Type: application/json" http://localhost:8000/movies/1

# Delete a movie
curl -X DELETE http://localhost:8000/movies/1
```

---

## Error Handling

- `404 Not Found` for non-existent movie IDs
- `400 Bad Request` for invalid JSON input
- All responses include `Content-Type: application/json`

---

## Contributing

Contributions are welcome! You can:
- Refactor and modularize the code
- Add persistent database support (e.g., PostgreSQL)
- Improve validation and error handling
- Add tests and CI integration

---

## License

Distributed under the MIT License.

---

## 👣 Next Steps

- Implement persistent storage
- Add unit tests
- Swagger/OpenAPI documentation
- Authentication middleware (JWT)
