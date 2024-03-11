# Postgres Golang API with Fiber

This project implements a simple API using Golang and Fiber framework to interact with a PostgreSQL database. It provides endpoints to create, retrieve, update, and delete books from the database.

## Prerequisites

Before running the application, make sure you have the following installed:

- Golang
- PostgreSQL
- Fiber framework
- GORM (Golang Object-Relational Mapping library)

## Getting Started

1. Clone the repository:

    ```bash
    git clone <repository_url>
    ```

2. Navigate to the project directory:

    ```bash
    cd postgres-golang
    ```

3. Install dependencies:

    ```bash
    go mod tidy
    ```

4. Create a `.env` file in the root directory with the following environment variables:

    ```
    DB_HOST=<database_host>
    DB_PORT=<database_port>
    DB_USER=<database_user>
    DB_PASSWORD=<database_password>
    DB_DBNAME=<database_name>
    DB_SSLMODE=<ssl_mode>
    ```

5. Run the application:

    ```bash
    go run main.go
    ```

## API Endpoints

### Create Book

- **URL:** `/api/create_books`
- **Method:** `POST`
- **Request Body:**
    ```json
    {
        "author": "Author Name",
        "title": "Book Title",
        "publisher": "Publisher Name"
    }
    ```

### Delete Book

- **URL:** `/api/delete_book/:id`
- **Method:** `DELETE`
- **URL Params:** `id=[integer]`

### Get Book by ID

- **URL:** `/api/get_books/:id`
- **Method:** `GET`
- **URL Params:** `id=[integer]`

### Get All Books

- **URL:** `/api/books`
- **Method:** `GET`

## Directory Structure

- `main.go`: Entry point of the application.
- `models/`: Contains database models and migration functions.
- `storage/`: Contains database connection setup.
- `.env`: Environment variables configuration file.

## Database Migration

The application automatically migrates the database schema using GORM's AutoMigrate feature. It creates a `Books` table with columns for `ID`, `Author`, `Title`, and `Publisher`.

## Contributing

Contributions are welcome! Feel free to open issues or submit pull requests.