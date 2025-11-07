# WS5 Movie API

This is a simple REST API built with **Node.js**, **Express**, and **MongoDB (Mongoose)** as part of the WS5 assignment.  
The API supports full CRUD operations for movies.

---

##  Requirements

Before running the project, make sure you have installed:

- **Node.js LTS**
- **npm** (comes with Node.js)
- **MongoDB Community Server** running locally  
  Default local URI: `mongodb://127.0.0.1:27017/ws5_movies`

---

##  Installation

Clone the project and install dependencies:

```bash
npm install
```

---

##  Environment Variables

Create a new file called **.env** in the project root:

```
MONGODB_URI=mongodb://127.0.0.1:27017/ws5_movies
PORT=3000
```

A template file **.env.example** is included for reference.

---

##  Running the Server

Start MongoDB (if not running):

```bash
brew services start mongodb-community
```

Start the API:

```bash
npm start
```

Server runs at:

```
http://localhost:3000
```

Test homepage:

```
curl http://localhost:3000
```

You should see:

```json
{ "message": "WS-5 Movie API running" }
```

---

##  API Endpoints

### ➤ Get all movies
```
GET /api/movies
```

Example:
```bash
curl http://localhost:3000/api/movies
```

---

### ➤ Get movie by ID
```
GET /api/movies/:id
```

Example:
```bash
curl http://localhost:3000/api/movies/MOVIE_ID
```

---

### ➤ Create a movie
```
POST /api/movies
```

Body example:
```json
{
  "title": "Test Movie",
  "year": 2024
}
```

Curl example:
```bash
curl -X POST http://localhost:3000/api/movies \
  -H "Content-Type: application/json" \
  -d '{"title":"Test Movie","year":2024}'
```

---

### ➤ Update a movie
```
PUT /api/movies/:id
```

Example:
```bash
curl -X PUT http://localhost:3000/api/movies/MOVIE_ID \
  -H "Content-Type: application/json" \
  -d '{"rating": 8.2}'
```

---

### ➤ Delete a movie
```
DELETE /api/movies/:id
```

Example:
```bash
curl -X DELETE http://localhost:3000/api/movies/MOVIE_ID
```

---

##  Project Structure

```
ws5-movie-api/
│── server.js
│── package.json
│── package-lock.json
│── .gitignore
│── .env.example
│── README.md
└── node_modules/
```

---

##  Notes

- `.env` is **not** included in the repository (ignored with `.gitignore`).
- `.env.example` shows required environment variables.
- The server automatically connects to your local MongoDB instance.

---

##  License

This project is created for educational purposes as part of the WS5 assignment.
