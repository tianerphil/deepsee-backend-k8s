Full Stack Overview
Components
Backend: Built with FastAPI, it provides a JSON-based web API.
2. Frontend: Developed using React, it interacts with the backend API.
Database: PostgreSQL is used for data storage.
Task Queue: Celery is used for background task processing.
Reverse Proxy: Traefik is used for routing and load balancing.
Key Technologies
FastAPI: For building the backend API.
React: For the frontend application.
Docker Compose: For container orchestration.
Celery: For asynchronous task processing.
Traefik: For reverse proxy and load balancing.
---
Configuration and Setup
Prerequisites
Docker: Ensure Docker is installed on your system.
Poetry: Used for Python package and environment management.
Environment Configuration
.env File: Configure environment variables in the .env file. Key variables include:
RUNPOD_ENDPOINT_URL
RUNPOD_ENDPOINT_ID
RUNPOD_API_KEY
SECRET_KEY
FIRST_SUPERUSER_PASSWORD
POSTGRES_PASSWORD
Docker Compose Override: Customize local development settings in docker-compose.override.yml.

Starting the Stack
Build and Start Containers:

1. **Build and Start Containers**:
   ```bash
   docker compose build --no-cache
   docker compose up -d
   ```
2. Access Services:
Frontend: http://localhost
Backend API: http://localhost/api/
Swagger UI: http://localhost/docs
Adminer: http://localhost:8080
Traefik Dashboard: http://localhost:8090

3. Check Logs:
 
3. **Check Logs**:

   docker compose logs

4. Access Specific Service Logs:

 docker compose logs backend


 5. runpod api health check
   curl -X GET "https://api.runpod.ai/v2/YOUR_ENDPOINT_ID/health" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -v