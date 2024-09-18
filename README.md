# RentHub Platform

This project is a rental-focused real estate platform, where users can list, search, and rent houses. The system is built with a microservices architecture and aims to provide a seamless experience for both property owners and tenants.

## Key Features

- **Property Accommodations**: Property owners can list their houses for rent, including details such as location, price, and amenities.
- **Property Search**: Users can search for rental properties based on location, price range, and other filters.
- **Map Integration**: View properties on an interactive map.
- **Price Estimation**: Offers price comparisons and market trends for rental properties in the same area.
- **User Profiles**: Both renters and landlords can manage their profiles, including booking history and listed properties.
- **Reviews and Ratings**: Tenants can leave reviews and rate properties after their rental experience.
- **Online Payments**: Secure payment integration for rent and deposits.
- **Authentication and Security**: JWT-based authentication for secure user access.

## Tech Stack

- **Golang**: Backend development and microservices.
- **gRPC**: For internal communication between services.
- **Protocol Buffers**: Service definitions.
- **PostgreSQL**: To store user data.
- **MongoDB**: To store property and booking data.
- **Gin Framework**: API Gateway and routing.
- **Redis**: Caching layer for optimizing performance.
- **Docker & Docker Compose**: Containerization and local development.
- **Kafka / RabbitMQ**: Message queue for asynchronous tasks.
- **Casbin**: Role-based access control.
- **Swagger**: API documentation.
- **JWT**: Authentication and authorization management.
- **Google Maps / Leaflet.js**: Map integration for property locations.
- **Stripe / PayPal**: Secure online payment processing.

## Microservices

1. **Auth Service**: Handles user registration, login, and JWT authentication.
2. **Accommodation Service**: Manages property Accommodations,house bookings, CRUD operations, and property search, availability checks, and conflicts.
3. **PayRate Service**: Manages property reviews and ratings. Integrates with Stripe or PayPal for handling rent and deposits.
4. **API Gateway**: Routes incoming HTTP requests to the appropriate microservices.

## Getting Started

### Prerequisites

- [Golang](https://golang.org/) (version >= 1.18)
- [PostgreSQL](https://www.postgresql.org/)
- [MongoDB](https://www.mongodb.com/)
- [Redis](https://redis.io/)
- [Docker](https://www.docker.com/)
- [Kafka](https://kafka.apache.org/) or [RabbitMQ](https://www.rabbitmq.com/)

### Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/yourusername/rent-a-house.git
    cd rent-a-house
    ```

2. Initialize submodules:

    ```bash
    git submodule init
    git submodule update
    ```

3. Run the services using Docker Compose:

    ```bash
    docker-compose up --build
    ```

4. Migrate the databases for each service:

    ```bash
    cd auth-service && go run cmd/migrate.go
    cd Accommodation-service && go run cmd/migrate.go
    ```

### API Documentation

API documentation is available through Swagger. Access it at:

- **Auth Service**: `http://localhost:8080/swagger/index.html`
- **Accommodation Service**: `http://localhost:8081/swagger/index.html`
- **PayRate Service**: `http://localhost:8081/swagger/index.html`

### Running Tests

To run unit and integration tests, use the following command:

```bash
go test ./...

### Project Structure
```bash
go test ./...


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


