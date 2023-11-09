# Overview

This repository encompasses a cloud project that involves containerization and orchestration of three distinct ping-pong applications (Java, Python, and JavaScript) alongside an Nginx configuration acting as a reverse proxy. The goal is to create Docker files for each application, build corresponding images, and assess their functionality within containers. Additionally, Nginx is tasked with serving as a reverse proxy and hosting a static HTML page, as well as facilitating the download of content from an external directory.

# Getting Started

Follow the steps below to set up and run the ping-pong applications in containers.

# Docker Files

Four Docker files need to be created:

java-pong-ping
    - Endpoint: /ping
    - Method: GET
    - Port: 8001

python-pong-ping
    - Endpoints:
        /ping (Method: GET)
        /echo (Method: POST, Payload: {"echo": "text"})
    - Port: 8002

js-pong-ping
    - Endpoint: /ping
    - Method: GET
    - Port: 8003

nginx
    Responsibilities:
        - Act as a reverse proxy for the applications
        - Host a static HTML page
        - Host contents of an external directory for download
