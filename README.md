# Energy Management System (Distributed Systems)

## Assignment Overview
This project implements an **Energy Management System** that allows authenticated users to access, monitor, and manage smart energy metering devices.
The system is designed as a set of loosely coupled, containerized microservices, orchestrated through a reverse proxy and an API Gateway.

## Architecture
The system follows a microservices architecture using the **Request-Reply Communication Paradigm**. All components are deployed independently using Docker.



### System Components
The solution includes the following distinct components:
1.  **Frontend Application (Web Client)**: A browser-based interface that manages user interactions and restricts access based on roles[cite: 22].
2.  **API Gateway & Reverse Proxy**: Acts as the entry point, routing requests and performing validation and security policies[cite: 23].
3.  **Microservices Layer**:
    * **User Management Service**: Handles CRUD operations for user accounts.
    * **Device Management Service**: Handles CRUD operations for devices and mapping to users.
    * **Authorization Service**: Handles login, registration, and token generation (JWT).

## User Roles & Functionalities
The platform supports two types of users:

### 1. Administrator
* **CRUD on Users**: Create, read, update, and delete user accounts.
* **CRUD on Devices**: Create, read, update, and delete smart devices.
* **Mapping**: Associate specific devices with specific users.

### 2. Client 
* **Login**: Secure authentication.
* **View Devices**: See a list of smart energy devices assigned to their account.

## Tech Stack
The following technologies were used (or recommended) for implementation:

* **Deployment**: Docker (Mandatory) 
* **Backend**: Java Spring Boot (REST)
* **Frontend**: ReactJS
* **Database**: PostgreSQL / MySQL
* **Reverse Proxy**: Traefik
* **Communication**: RESTful APIs

## Data Models
* **User**: `ID`, `username`, `password` (minimum attributes).
* **Device**: `ID`, `name`, `maximum consumption` (minimum attributes).

## How to Run
1.  **Clone the repository**:
    ```bash
    git clone <repository_url>
    ```
2.  **Build Docker Containers**:
    Ensure Docker Desktop is running.
    ```bash
    docker-compose build
    ```
3.  **Start the System**:
    ```bash
    docker-compose up
    ```
4.  **Access the Application**:
    * Frontend: `http://localhost:3000` (Default)
    * API Documentation: `http://localhost:8080/swagger-ui.html` (If configured) 

## Deliverables
This repository includes:
* Source code for all microservices.
* `docker-compose.yml` for orchestration.
* UML Deployment Diagram.
* Database dumps.
