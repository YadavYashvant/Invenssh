👷‍♀️ UNDER CONSTRUCTION ⚠️
# Invenssh

**Invenssh** is a **Product Inventory Management System** built with **Spring Boot** and a **Microservices** architecture. It uses **MongoDB** as the database, **Docker Compose** for containerization, and **Kubernetes** for orchestration. Invenssh allows businesses to manage product inventory efficiently, providing a range of operations for managing product information, stock quantities, and pricing.

## Table of Contents

- [Features](#features)
- [Architecture](#architecture)
- [Technologies Used](#technologies-used)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [API Documentation](#api-documentation)
- [Running with Docker Compose](#running-with-docker-compose)
- [Running with Kubernetes](#running-with-kubernetes)
- [Contributing](#contributing)
- [License](#license)

## Features

- **Microservices Architecture**: Modular design separates functionality across distinct services for scalability and maintainability.
- **Product Management**: Full CRUD operations for managing product details.
- **Inventory Tracking**: Real-time updates on stock availability.
- **Pricing Management**: Dynamically handle product pricing.
- **Containerization**: Dockerized services for streamlined deployment and environment consistency.
- **Orchestration**: Kubernetes allows easy scaling and management of containers.

## Architecture

Invenssh is built as a microservices-based application with each service handling a specific domain:

- **Product Service**: Manages product metadata (name, description, etc.).
- **Inventory Service**: Tracks and updates product quantities in stock.
- **Pricing Service**: Manages product pricing information.
- **Gateway Service**: Acts as an API gateway, routing client requests to the appropriate services.
- **MongoDB Database**: A NoSQL database for document-based data storage used by each service.

### Architecture Diagram
![Architecture Diagram](link_to_architecture_diagram.png)

## Technologies Used

- **Java 17** & **Spring Boot**: The primary framework for building and structuring microservices.
- **MongoDB**: Document-oriented NoSQL database.
- **Docker** & **Docker Compose**: For containerization of services.
- **Kubernetes**: Orchestration platform for deploying and managing containers.

## Getting Started

### Prerequisites

- Java 17 or higher
- Docker and Docker Compose
- Kubernetes (Minikube, or any other Kubernetes setup)
- MongoDB (if testing locally without Docker)

### Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/invenssh.git
   cd invenssh
   ```

2. **Build the Services**:
   ```bash
   ./mvnw clean install
   ```

## API Documentation

Each service in Invenssh offers a REST API for managing products, inventory, and pricing.

### Example Endpoints

- **Product Service**:
  - `POST /products`: Add a new product to the inventory.
  - `GET /products/{id}`: Retrieve details of a specific product.
  
- **Inventory Service**:
  - `GET /inventory/{productId}`: Check the stock level for a specific product.
  
- **Pricing Service**:
  - `GET /pricing/{productId}`: Retrieve pricing details for a specific product.

API documentation is accessible via **Swagger UI** at `{host}:{port}/swagger-ui.html` for each service.

## Running with Docker Compose

To run Invenssh using Docker Compose:

1. **Start All Services**:
   ```bash
   docker-compose up --build
   ```

2. **Access Each Service**: Services can be accessed on `http://localhost:{service_port}` as configured in `docker-compose.yml`.

## Running with Kubernetes

To deploy Invenssh on Kubernetes:

1. **Apply Kubernetes Configurations**:
   ```bash
   kubectl apply -f k8s/
   ```

2. **Access Services**: Kubernetes services can be accessed through NodePort or LoadBalancer, depending on your setup.

## Contributing

Contributions to Invenssh are welcome! Please open an issue or submit a pull request to propose new features or report bugs.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for more information.
