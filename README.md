# FastAPI Starter by Akaday

## Overview
**FastAPI Starter by Akaday** is a template designed to kickstart FastAPI projects quickly and efficiently. This template provides a solid foundation with essential features and configurations, making it easier to develop robust and scalable FastAPI applications.

## Features
- **FastAPI Setup**: A basic setup to get started with FastAPI.
- **Docker Support**: Pre-configured Dockerfile for containerization.
- **GitHub Actions**: Automated workflows for building and deploying Docker images.
- **Modular Structure**: Organized project structure to maintain code clarity and ease of development.

## Project Structure
```plaintext
fastapi_project/
├── app/
│   ├── __init__.py
│   ├── main.py
│   ├── api/
│   │   ├── __init__.py
│   │   └── endpoints/
│   │       └── __init__.py
│   ├── core/
│   │   ├── __init__.py
│   │   └── config.py
│   ├── models/
│   │   ├── __init__.py
│   │   └── user.py
│   ├── schemas/
│   │   ├── __init__.py
│   │   └── user.py
├── requirements.txt
├── Dockerfile
├── .env
├── .gitignore
└── README.md
```

## Setup Instructions

### Prerequisites
- Python 3.7+
- FastAPI
- Uvicorn
- Docker (optional, for containerization)

### Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/akaday/FastAPI-Starter.git
    cd FastAPI-Starter
    ```

2. Create and activate a virtual environment:
    ```sh
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. Install the dependencies:
    ```sh
    pip install -r requirements.txt
    ```

### Authentication and Validation Setup

1. Install additional dependencies:
    ```sh
    pip install passlib[bcrypt] python-jose
    ```

2. Update the `app/main.py` file to include authentication and validation routes.

### Running the Application

1. Start the FastAPI application:
    ```sh
    uvicorn app.main:app --reload
    ```

2. Access the application at `http://127.0.0.1:8000`.

## Usage Instructions

### Authentication

- **Login**: Obtain a JWT token by providing username and password.
    ```sh
    POST /token
    {
        "username": "user@example.com",
        "password": "password"
    }
    ```

- **Get Current User**: Retrieve the current authenticated user's information using the JWT token.
    ```sh
    GET /users/me/
    Authorization: Bearer <token>
    ```

### User Management

- **Create User**: Create a new user by providing name, email, and password.
    ```sh
    POST /users/
    {
        "name": "John Doe",
        "email": "john.doe@example.com",
        "password": "password"
    }
    ```

## Deployment

Consider deploying your app using services like Heroku, AWS, or Azure. Follow their respective documentation for deployment instructions.
