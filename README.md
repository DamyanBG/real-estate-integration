# Real Estate App Docker Integration

This Docker Compose configuration sets up a development environment for a Real Estate web application with separate backend and frontend containers. You can choose to run the full integration or just the backend component.

## Prerequisites

Before using this Docker Compose configuration, make sure you have the following prerequisites installed on your system:

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

## Getting Started

1. Clone this repository to your local machine.

2. Create a `.env` file in the `./real-estate-flask-rest-api` directory with the following environment variables for the Flask backend. Replace the placeholders with your actual configuration:

   ```env
   POSTGRES_USER=your_postgres_user
   POSTGRES_PASSWORD=your_postgres_password
   POSTGRES_DB=your_postgres_db

Usually the container for the database creates default configuration for PostgreSQL and you can use default credentioals.

## Building the Containers

Before running the Docker Compose commands, you may need to build the Docker containers if they haven't been built already. Follow these steps to build the containers:

1. Navigate to the root directory where you have the `docker-compose.yml` file.

2. Open your terminal or command prompt.

3. To build the containers for the backend and frontend (if not already built), use the following commands:

   ```bash
   docker-compose build flask-be fe-react
    ```

## Usage

### Full Integration

To run both the backend and frontend components together, use the following command:

```bash
docker-compose up -d
```

This command starts all containers defined in the docker-compose.yml file. Once the containers are up and running, you can access the web application at http://localhost:3000.

### Backend Integration Only

If you want to run only the backend component without the frontend, use the following command:

```bash
docker-compose up -d flask-be postgres
```

This command starts the flask-be (backend) and postgres (database) containers while excluding the fe-react (frontend) container. The Flask backend can be accessed at http://localhost:5000.