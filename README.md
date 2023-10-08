# Books API - README

Welcome to the Books API repository! This Express.js application provides a simple API for managing a collection of books. Below, you'll find instructions on how to run the server and interact with the API endpoints.

## Prerequisites

Before running the application, make sure you have the following installed on your system:

- [Node.js](https://nodejs.org/): The application is built with Node.js.

## How to Run

1. **Clone the Repository:**

   ```bash
   git clone <repository-url>
   ```

   This will clone the repository to your local machine.

2. **Navigate to the Project Directory:**

   ```bash
   cd <repository-folder>
   ```

3. **Install Dependencies:**

   ```bash
   npm install
   ```

4. **Run the Server:**

   ```bash
   node index.js
   ```

   The server will start on port 3000 by default. You can change the port in the `app.listen()` statement in the `index.js` file if needed.

## API Endpoints

### 1. Get All Books

- **Endpoint:** `/books`
- **Method:** `GET`
- **Description:** Get a list of all books. Optionally, you can filter books by availability by using query parameters:
  - `avail=true` - Get available books
  - `avail=false` - Get unavailable books

### 2. Get a Book by ID

- **Endpoint:** `/books/:id`
- **Method:** `GET`
- **Description:** Get a specific book by its ID.

### 3. Add a New Book

- **Endpoint:** `/books`
- **Method:** `POST`
- **Description:** Add a new book to the collection. Send a JSON object with book details in the request body.

### 4. Update a Book

- **Endpoint:** `/books/:id`
- **Method:** `PUT`
- **Description:** Update an existing book by its ID. Send a JSON object with the updated book details in the request body.

### 5. Delete a Book

- **Endpoint:** `/books/:id`
- **Method:** `DELETE`
- **Description:** Delete a book from the collection by its ID.

## Example Usage

To interact with the API endpoints, you can use tools like `curl` or API clients like [Postman](https://www.postman.com/). Below are some example commands using `curl`:

### Get All Books

```bash
curl http://localhost:3000/books
```

### Get Available Books

```bash
curl http://localhost:3000/books?avail=true
```

### Get a Book by ID

```bash
curl http://localhost:3000/books/1
```

### Add a New Book

```bash
curl -X POST -H "Content-Type: application/json" -d '{"id": "7", "title": "New Book", "author": "Author Name", "publisher": "Publisher Name", "isbn": "123-456-7890", "avail": "true", "who": "", "due": ""}' http://localhost:3000/books
```

### Update a Book

```bash
curl -X PUT -H "Content-Type: application/json" -d '{"title": "Updated Book Title"}' http://localhost:3000/books/7
```

### Delete a Book

```bash
curl -X DELETE http://localhost:3000/books/7
```
