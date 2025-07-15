# FastAPI Application Docker Setup

## Overview
This project is a FastAPI-based application configured to run using Docker and Docker Compose. This README provides instructions on how to run the application using Docker Compose and manage the containers.

## Prerequisites
- Docker installed on your machine. You can download it from [https://www.docker.com/get-started](https://www.docker.com/get-started)
- Docker Compose installed (usually comes with Docker Desktop)

## Environment Variables
The application uses environment variables defined in the `.env` file. Make sure to create and configure this file with the necessary variables before running the containers.

## Run with Docker Compose
To start the application and its dependencies (e.g., PostgreSQL database) using Docker Compose, run:

```bash
docker-compose up --build
```

This command will build the images if necessary and start the containers. The FastAPI app will be accessible on the port defined by the `fastapi_port` environment variable.

## Stop and Remove Containers
To stop the running containers, press `Ctrl+C` in the terminal where Docker Compose is running, or run:

```bash
docker-compose down
```

This will stop and remove the containers, but the database volume will persist.

## Data Persistence
The PostgreSQL database data is persisted in a Docker volume named `postgres_data`. This ensures your data is not lost when containers are stopped or removed.

## Additional Commands
- To view running containers:

```bash
docker ps
```

- To view all containers (including stopped):

```bash
docker ps -a
```

- To remove unused Docker volumes:

```bash
docker volume prune
```

## Notes
- The application code is mounted as a volume inside the container (`.:/app`), so changes to the code on your host machine will reflect inside the container immediately.
- Make sure the `.env` file is properly configured with all required environment variables before starting the containers.

---
This README provides the basic Docker setup and usage instructions for this FastAPI application.
