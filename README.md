# Django Application with Docker

This project is a Django application running in Docker containers. The application is set up to use PostgreSQL as the database.

## Prerequisites

Before you start, ensure that you have the following installed:
- Docker
- Docker Compose

## Getting Started

Follow these steps to get the application up and running:

### 1. Clone the repository

Clone the repository to your local machine:

```bash
git clone https://github.com/firdavs244/DjangoAdminLMS.git
cd DjangoAdminLMS
```

### 2. Build and start the containers

Run the following command to build and start the Docker containers:

```bash
docker-compose up -d --build
```

This will:
- Build the Docker images as per the `Dockerfile` and `docker-compose.yml` configuration.
- Start the containers in detached mode.

### 3. Run database migrations

After the containers are up and running, apply the database migrations with this command:

```bash
docker-compose exec web python manage.py migrate
```

This will set up the database schema.

### 4. Create a superuser

Next, create a superuser for accessing the Django admin panel:

```bash
docker-compose exec web python manage.py createsuperuser
```

You will be prompted to enter a username, email, and password for the superuser.

### 5. Access the application

Once the application is running, you can access it in your browser at:

[http://localhost:8000](http://localhost:8000)

### Environment Variables

The application uses environment variables for configuring the PostgreSQL database connection. These are defined in the `docker-compose.yml` file.

- **POSTGRES_USER**: The PostgreSQL user (default: `root`)
- **POSTGRES_PASSWORD**: The PostgreSQL user's password (default: `root`)
- **POSTGRES_DB**: The database name (default: `lms_db`)

### Stopping the containers

To stop the running containers, use:

```bash
docker-compose down
```

This will stop and remove all the containers, networks, and volumes defined in the `docker-compose.yml` file.

### Docker Compose commands summary

- **Start the containers**:
  ```bash
  docker-compose up -d --build
  ```

- **Run database migrations**:
  ```bash
  docker-compose exec web python manage.py migrate
  ```

- **Create superuser**:
  ```bash
  docker-compose exec web python manage.py createsuperuser
  ```

- **Stop the containers**:
  ```bash
  docker-compose down
  ```
