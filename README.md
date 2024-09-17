# Rent a House Backend

This is the backend service for the "Rent a House" platform, which allows users to list, search, and book houses for rent. The project is designed using a microservices architecture.

## Tech Stack

- **Golang**: For all microservices.
- **gRPC**: Service-to-service communication.
- **Protocol Buffers**: For defining service messages.
- **PostgreSQL**: To store user-related data.
- **MongoDB**: To store booking and service provider data.
- **Gin Framework**: For API Gateway and routing.
- **Database Migrations**: Using `golang-migrate` for schema versioning.
- **Swagger**: For API documentation.
- **JWT**: For user authentication and authorization.
- **Redis**: For caching and session management.
- **Docker & Docker Compose**: For containerization and local deployment.
- **Kafka or RabbitMQ**: For asynchronous messaging between services.
- **Casbin**: For role-based access control (RBAC).

## Microservices

1. **Auth Service**: Handles user registration, login, and JWT-based authentication.
2. **House Listing Service**: Manages house listings, CRUD operations, and searching/filtering of houses.
3. **Booking Service**: Manages house bookings, availability checks, and booking conflicts.
4. **Payment Service** (Optional): Integrates payment gateway and handles transaction records.
5. **API Gateway**: Routes incoming requests to appropriate microservices.

## Getting Started

### Prerequisites

- [Golang](https://golang.org/) (version >= 1.18)
- [PostgreSQL](https://www.postgresql.org/)
- [MongoDB](https://www.mongodb.com/)
- [Redis](https://redis.io/)
- [Kafka](https://kafka.apache.org/) or [RabbitMQ](https://www.rabbitmq.com/)
- [Docker](https://www.docker.com/)

### Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/yourusername/rent-a-house.git
    cd rent-a-house
    ```

2. Initialize submodules for each microservice:

    ```bash
    git submodule init
    git submodule update
    ```

3. Run the services using Docker Compose:

    ```bash
    docker-compose up --build
    ```

4. Migrate the database for each service:

    ```bash
    cd auth-service && go run cmd/migrate.go
    cd house-listing-service && go run cmd/migrate.go
    ```

### API Documentation

The API is documented using Swagger. Once the server is running, you can access the API docs at:

- **Auth Service**: `http://localhost:8080/swagger/index.html`
- **House Listing Service**: `http://localhost:8081/swagger/index.html`
- **Booking Service**: `http://localhost:8082/swagger/index.html`

### Service Communication

Services communicate with each other using **gRPC** and are defined using **Protocol Buffers**. For asynchronous tasks like notifications and order processing, **Kafka** or **RabbitMQ** is used.

### Running Tests

Run the following command to execute unit and integration tests:

```bash
go test ./...


### Project Structure
.
├── cmd                # Entry points for each microservice
├── config             # Configuration files and environment setup
├── controllers        # API controllers for handling requests
├── models             # Database models and schemas
├── routes             # API routes definitions
├── services           # Business logic and service layer
├── proto              # Protocol Buffers definitions
├── Dockerfile         # Dockerfile for containerization
├── docker-compose.yml # Docker Compose configuration
└── README.md          # Project documentation


