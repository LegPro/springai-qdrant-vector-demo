# SpringAI Qdrant Vector Demo

This project demonstrates the integration of [Qdrant](https://qdrant.tech/), an open-source vector search engine, with Spring Boot to build a vector store service. The application provides endpoints for loading documents into the Qdrant vector store and searching for similar documents using vector embeddings.

## Prerequisites

Before running the project, ensure you have the following installed:

- **Java 21**: Required to build and run the Spring Boot application.
- **Maven**: Used to build the project.
- **Docker**: Required to run Qdrant in a container.
- **Spring Boot**: A Java-based framework to create microservices.
- **Spring AI**: Used for managing AI interactions and embeddings.

## Setting Up Qdrant with Docker

Qdrant is an efficient vector database for storing and retrieving high-dimensional vectors. Follow the steps below to install and run Qdrant using Docker.

### Quick Docker Command to Install Qdrant

Run the following command to start Qdrant:

```bash
docker run -p 6333:6333 -p 6334:6334 -v ./qdrant_storage:/qdrant/storage:z qdrant/qdrant
```
This command will run Qdrant on your local machine, exposing the service on ports 6333 (REST API) and 6334 (gRPC API).

## Project Setup
Clone the Repository:
```bash
git clone https://github.com/LegPro/springai-qdrant-vector-demo.git
cd springai-qdrant-vector-demo
```
Alternatively, you can set the API key as an environment variable:
```bash
export SPRINGAI_API_KEY=your_api_key
```
## Configure Qdrant Connection:

In the application.properties file, ensure the Qdrant connection details are configured properly.



## Running the Application

To run the Spring Boot application, execute the following command:

```bash
mvn spring-boot:run
```

## Endpoints
Load Documents: Load vectorized documents into the Qdrant vector store.
```bash
GET http://localhost:8080/load
```

Search Documents: Search for similar documents based on a vector query.
```bash
GET http://localhost:8080/search?query=<your-search-query>
```

