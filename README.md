# Project Repository: Multilingual Ping-Pong Cloud Challenge

## Overview
This repository encompasses a cloud project that involves containerization and orchestration of three distinct ping-pong applications (Java, Python, and JavaScript) alongside an Nginx configuration acting as a reverse proxy. The goal is to create Docker files for each application, build corresponding images, and assess their functionality within containers. Additionally, Nginx is tasked with serving as a reverse proxy and hosting a static HTML page, as well as facilitating the download of content from an external directory.

## Getting Started
Follow the steps below to set up and run the ping-pong applications in containers.

### Docker Files
Four Docker files need to be created:

1. **java-pong-ping**
    - Endpoint: /ping
    - Method: GET
    - Port: 8001

2. **python-pong-ping**
    - Endpoints:
        - /ping (Method: GET)
        - /echo (Method: POST, Payload: {"echo": "text"})
    - Port: 8002

3. **js-pong-ping**
    - Endpoint: /ping
    - Method: GET
    - Port: 8003

4. **nginx**
    - Responsibilities:
        - Act as a reverse proxy for the applications
        - Host a static HTML page
        - Host contents of an external directory for download

### Running Containers
After creating the Docker files, follow these general steps to run the containers:

```bash
# Build Docker images
docker build -t ping-pong-java .
docker build -t ping-pong-python .
docker build -t ping-pong-js .

# Run Docker containers
docker run --network=DockerNetwork -p 8001:8001 java-pong-ping
docker run --network=DockerNetwork --alias=pythonapp -p 8002:8002 ping-pong-python
docker run -d -p 8003:8003 js-pong-ping
docker run --network=DockerNetwork -p 8080:8080 -v database-PATH /shared nginx-config
```

### Application Endpoints

1. **Java Pong Ping**
    - /ping (GET): Receive "pong" as a response
    - URL: http://localhost:8001/ping

2. **Python Pong Ping**
    - /ping (GET): Receive "pong" as a response
    - /echo (POST): Receive "text" as a response (Payload: {"echo": "text"})
    - URL: http://localhost:8002/ping and http://localhost:8002/echo

3. **JS Pong Ping**
    - /ping (GET): Receive "pong" as a response
    - URL: http://localhost:8003/ping

### Nginx Configuration

- Nginx is configured to fulfill the following responsibilities:
    - act as a reverse proxy
    - Host a static HTML page.
    - Host contents of an external directory for download.

### Note


### results

- java output
![java output](https://github.com/AlirezaNR1/Docker-Cloud-Orchestration/assets/141549257/5d3bff00-a8cb-40b4-bbf7-7daf5f5cc92c)

- python output
![python echo output](https://github.com/AlirezaNR1/Docker-Cloud-Orchestration/assets/141549257/29c3c60c-6824-4dab-b338-e93a0d5b95d4)
![python output](https://github.com/AlirezaNR1/Docker-Cloud-Orchestration/assets/141549257/990c1557-b848-4f3d-abd5-579b1a12698c)

- js output
![js output](https://github.com/AlirezaNR1/Docker-Cloud-Orchestration/assets/141549257/eb01088f-1a07-498e-bd0e-53b9e1d5319a)

- nginx output
![nginx java](https://github.com/AlirezaNR1/Docker-Cloud-Orchestration/assets/141549257/bb360d9e-821f-4fd3-847d-ffd8d0bf77b6)

Feel free to reach out if you encounter any issues or have further questions! Happy coding!
