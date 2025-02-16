# Library API

A simple RESTful API built with Go and Gin for managing a book library. This API allows users to retrieve book information, add new books, check out books, and return books.

## Features

- Get a list of available books
- Retrieve a book by its ID
- Add a new book to the library
- Check out a book
- Return a book

## Installation

1. Clone the repository:
   ```sh
   git clone https://github.com/gfarida/library-api.git
   cd library-api

2. Install dependencies:
    ```sh
    go mod tidy
    ```


3. Run the server:
    ```sh
    go run main.go
    ```
By default, the server runs on localhost:8080.

## API Endpoints

1. Get all books

    Request:

    ```sh
    curl -X GET "http://localhost:8080/books"
    ```

2. Get a book by ID
    Request:

    ```sh
    curl -X GET "http://localhost:8080/books/2"
    ```

3. Add a new book
    Request:

    ```sh
    curl -X POST "http://localhost:8080/books" -H "Content-Type: application/json" -d '{
    "id": "4",
    "title": "1984",
    "author": "George Orwell",
    "quantity": 3
    }'
    ```

4. Check out a book
    Request:

    ```sh
    curl -X PATCH "http://localhost:8080/checkout?id=2"
    ```

5. Return a book
    Request:

    ```sh
    curl -X PATCH "http://localhost:8080/return?id=2"
    ```

## Notes
    1. If a book does not exist, the API returns a 404 Not Found response.
    2. If the quantity of a book is 0, it cannot be checked out.
    3. The id parameter in checkout and return operations should match an existing book.
    4. The application stores data in memory and does not persist changes across restarts.
