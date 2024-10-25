# Naming-Server

The Naming Server handles service discovery for all microservices using Spring Cloud Netflix Eureka.

## Getting Started

The Naming Server registers microservices, allowing dynamic service discovery and load balancing across services.

### Prerequisites

- Java 17
- Maven
- Docker (optional)

### Local Setup Without Docker

1. **Clone the repository**:
    ```bash
    git clone <repository-url>
    cd naming-server
    ```

2. **Configure application properties**: Update `src/main/resources/application.properties`:
    ```properties
    spring.application.name=naming-server
    server.port=8761
    eureka.client.register-with-eureka=false
    eureka.client.fetch-registry=false
    ```

3. **Build the application**:
    ```bash
    mvn clean install
    ```

4. **Run the application**:
    ```bash
    mvn spring-boot:run
    ```

### Local Setup With Docker

1. **Build the Docker image**:
    ```bash
    docker build -t naming-server .
    ```

2. **Run the Docker container**:
    ```bash
    docker run -p 8761:8761 naming-server
    ```

Your Naming Server should now be available at `http://localhost:8761`.
