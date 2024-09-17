# Rent a House

This is the backend service for the "Rent a House" platform, which allows users to list, search, and book houses for rent.

## Tech Stack

- **Programming Language**: Golang
- **Database**: PostgreSQL
- **Cache**: Redis
- **Authentication**: JWT (JSON Web Tokens)
- **API Documentation**: Swagger
- **Deployment**: Docker, Docker Compose
- **Testing**: Unit and Integration Tests

## Features

- User registration and authentication
- Add, edit, and delete house listings
- Search and filter houses by location, price, type, etc.
- Book a house for specific dates
- Handle booking conflicts
- Payment integration (optional)
- Caching with Redis for better performance

## Getting Started

### Prerequisites

- [Golang](https://golang.org/) (version >= 1.18)
- [PostgreSQL](https://www.postgresql.org/)
- [Redis](https://redis.io/)
- [Docker](https://www.docker.com/)

### Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/yourusername/rent-a-house-backend.git
    cd rent-a-house-backend
    ```

2. Create a `.env` file for environment variables. You can use the `.env.example` file as a reference:

    ```bash
    cp .env.example .env
    ```

3. Run the services using Docker Compose:

    ```bash
    docker-compose up --build
    ```

4. Migrate the database:

    ```bash
    go run cmd/migrate.go
    ```

### API Documentation

The API is documented using [Swagger](https://swagger.io/). Once the server is running, you can access the API docs at:


### Database Schema

The database includes the following tables:

- **Users**: Stores user information and authentication data.
- **Houses**: Contains house listings with details like price, location, and description.
- **Bookings**: Manages booking records including booking dates, user information, and payment status.

### Running Tests

Run the following command to execute tests:

```bash
go test ./...

### Project Structure
.
├── cmd               # Entry point for the application
├── config            # Configuration files and environment setup
├── controllers       # API controllers
├── models            # Database models and schemas
├── routes            # API routes definitions
├── services          # Business logic and service layer
├── utils             # Utility functions
├── Dockerfile        # Dockerfile for containerization
├── docker-compose.yml# Docker Compose configuration
└── README.md         # Project documentation

