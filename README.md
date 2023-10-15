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
   ```

Usually the container for the database creates default configuration for PostgreSQL and you can use default credentioals.

## Environment variables

### Add variables when integrate only Backend

If you need to run only the backend, add .env file in ./real-estate-flask-rest-api/ and add these variables:

```env
DB_USER=your_postgres_user
DB_PASSWORD=your_postgres_password
DB_HOST=your_postgres_port
DB_NAME=your_postgres_db
JWT_KEY=some_JWT_KEY
NEXTCLOUD_USER=
NEXTCLOUD_PASSWORD=
```

Here you have to add the credentials for the back end. For Nextcloud - write me, I will give you my credentials for my cloud IF YOU NEED THEM REALLY.

In future I will add the Nextcloud as separate container.

On real-estate-react-app have committed .env file. The default domain for the Flask container is localhost:5000.

### Environment variables for Full integration

Follow the steps for integration of the backend + for the .env in the Front end add the name of the back end container.
You can see the name of the container with companes:

docker compose build
docker compose ps

## Building the Containers

Before running the Docker Compose commands, you may need to build the Docker containers if they haven't been built already. Follow these steps to build the containers:

1. Navigate to the root directory where you have the `docker-compose.yml` file.

2. Open your terminal or command prompt.

3. To build the containers for the backend and frontend, use the following commands:

   ```bash
   docker-compose build
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