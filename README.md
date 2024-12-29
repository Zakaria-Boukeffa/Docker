# **TodoApp**

TodoApp is a full-stack application for managing tasks, consisting of a Flask backend, an Angular frontend, and a MySQL database. The project is containerized using Docker and orchestrated with Docker Compose for ease of deployment and management.

---

## **Project Structure**

The project is organized into the following directories and files:

- **`backend/`**: Contains the Flask application that handles the API and business logic.
- **`frontend/`**: Contains the Angular application that provides the user interface.
- **`docker-compose.yml`**: Orchestrates all the services and dependencies.
- **`nginx.conf`**: Configuration file for Nginx, used as a reverse proxy.

---

## **Services**

The application stack includes the following services:

### **1. Backend**
- **Purpose**: Hosts the API using Flask.
- **Configuration**:
  - Built from the `Dockerfile` in `backend/`.
  - Uses environment variables to configure the Flask app and database connection.
  - Exposes port `5000` for API access.
- **Healthcheck**: Monitors API availability at `/health`.

### **2. Frontend**
- **Purpose**: Hosts the Angular application for the user interface.
- **Configuration**:
  - Built from the `Dockerfile` in `frontend/`.
  - Exposes port `4200` for the user interface.
- **Healthcheck**: Ensures the Angular app is reachable.

### **3. MySQL**
- **Purpose**: Provides the relational database for storing application data.
- **Configuration**:
  - Runs MySQL version 8.0.
  - Database credentials are defined in the `docker-compose.yml` file.
  - Persistent data is stored in the named volume `mysql_data`.

### **4. phpMyAdmin**
- **Purpose**: Provides a web-based interface to manage the MySQL database.
- **Configuration**:
  - Uses the phpMyAdmin image.
  - Accessible on port `8081`.

### **5. Nginx**
- **Purpose**: Acts as a reverse proxy for the backend and frontend.
- **Configuration**:
  - Configured with `nginx.conf`.
  - Exposes the main application on port `80`.

---

## **Setup Instructions**

### **Prerequisites**
Make sure you have the following installed:
- **Docker**: [Install Docker](https://www.docker.com/)
- **Docker Compose**: [Install Docker Compose](https://docs.docker.com/compose/)

### **Steps to Run**
1. Clone the repository:
   ```bash
   git clone <repository_url>
   cd <repository_folder>
 
  Start docker desktop 
  then in vscode , do 
 ```bash
  docker-compose up --build
