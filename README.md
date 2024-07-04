**Description**: This project sets up an Open-WebUI service and a Stable Diffusion service with an Nginx reverse proxy that uses SSL for secure connections. The Nginx server is configured to generate self-signed certificates if they do not exist, and the services are orchestrated using Docker Compose.

### Project Structure

- **open-webui**: A web UI service containerized and exposed on a configurable port.
- **nginx**: An Nginx container configured to proxy requests to the Open-WebUI and Stable Diffusion services with SSL termination.
- **stablediff**: A Stable Diffusion service containerized and exposed on a specific port.

### Key Components

1.  **Dockerfile.nginx**:
    
    - Builds an Nginx image with OpenSSL installed.
    - Generates self-signed SSL certificates.
    - Copies the main Nginx configuration file.
2.  **docker-compose.yml**:
    
    - Orchestrates the `open-webui`, `nginx`, and `stablediff` services.
    - Mounts necessary volumes and sets up port forwarding.
    - Ensures services are started in the correct order using `depends_on`.
3.  **nginx.conf**:
    
    - Configures Nginx to listen on ports 80 and 443.
    - Sets up SSL termination and proxy passes to the respective services.
  



### Setup Instructions

1.  **Clone the Repository**:
    
    sh
    
    `git clone https://github.com/yourusername/yourrepository.git cd yourrepository`
    
2.  **Build and Run the Services**:
    
    sh
    
    `docker-compose up --build`
    
3.  **Access the Services**:
    
    - Open-WebUI: `http://localhost:3000` (or configured port)
    - Stable Diffusion: `http://localhost:7860`
