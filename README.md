# compose.yaml

## Docker Compose Setup

This project contains a Docker Compose configuration that defines two Nginx services running on different ports.

### Services

1. **nginx1**  
   This service builds an Nginx container from a custom Dockerfile located in the current directory (`.`). The service is configured with the following settings:
   - **Build context**: The current directory (`.`).
   - **Dockerfile**: `Dockerfile` (located in the current directory).
   - **Container name**: `nginx_8855`.
   - **Ports**: This service binds port `80` inside the container to port `8855` on the host machine (`8855:80`).

2. **nginx2**  
   This service runs an Nginx container using the latest Nginx image from Docker Hub. The service is configured with the following settings:
   - **Image**: `nginx:latest`.
   - **Container name**: `nginx_9955`.
   - **Ports**: This service binds port `80` inside the container to port `9955` on the host machine (`9955:80`).

### Usage

To build and run the services, use the following command in the directory where your `docker-compose.yml` is located:

```bash
docker-compose up
```

This will spin up two Nginx instances, each accessible via the host machine on different ports:
- Nginx1: [http://localhost:8855](http://localhost:8855)
- Nginx2: [http://localhost:9955](http://localhost:9955)
