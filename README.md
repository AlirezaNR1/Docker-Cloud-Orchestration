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
docker build -t java-pong-ping -f Dockerfile.java .
docker build -t python-pong-ping -f Dockerfile.python .
docker build -t js-pong-ping -f Dockerfile.js .
docker build -t nginx-reverse-proxy -f Dockerfile.nginx .

# Run Docker containers
docker run -d -p 8001:8001 java-pong-ping
docker run -d -p 8002:8002 python-pong-ping
docker run -d -p 8003:8003 js-pong-ping
docker run -d -p 80:80 nginx-reverse-proxy
```
