# My Quasar Express App

This project consists of a Quasar (Vue.js) frontend and an Express.js backend, containerized with Docker.

## Prerequisites

- [Docker](https://www.docker.com/get-started) installed on your machine.

## How to Run

1.  **Build and Run**
    Open a terminal in the project root directory and run:

    ```bash
    docker-compose up --build
    ```

    This command will build the Docker images for both backend and frontend and start the containers.

2.  **Access the Application**

    - **Frontend**: Open your browser and go to [http://localhost:8080](http://localhost:8080)
    - **Backend API**: The API is available at [http://localhost:4000](http://localhost:4000) (e.g., [http://localhost:4000/api/demo](http://localhost:4000/api/demo))

3.  **Stop the Application**
    To stop the containers, press `Ctrl+C` in the terminal, or run:

    ```bash
    docker-compose down
    ```

## Project Structure

- `backend/`: Express.js server code.
- `frontend/`: Quasar Framework (Vue.js) frontend code.
- `docker-compose.yml`: Docker Compose configuration to manage both services.
