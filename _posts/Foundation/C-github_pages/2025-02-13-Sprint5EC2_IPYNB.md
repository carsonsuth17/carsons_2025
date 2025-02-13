# Cockpit: The Terminal for the Amazon EC2 Server

Inside the EC2 server, I have a Docker container running called **melodymates**, which is running on port `8404`.

## What is a Container?

A container is like a virtual computer that runs our backend server. When a request reaches the EC2 server on port `8404`, our **nginx** configuration helps route it to our container based on the unique port.

## Docker Basics

A Docker image acts as the blueprint for a virtual computer. Our container is running based on this "blueprint."

- `docker-compose down`: Stops and removes the container but keeps the image.
- `docker-compose build`: Creates a new Docker image, acting as a fresh blueprint.
- `docker-compose up`: Runs the container using the blueprint on port `8404`.

## How Requests Work

When someone makes a request to our DNS (instead of using an IP address, they type `melodymates.stu.nighthawkcodingsociety.com`), the following happens:

1. The request goes to our EC2 server.
2. NGINX routes it to the correct container.
3. The container processes the request and returns JSON data.
4. NGINX sends the JSON data back to the client (the requester).

## Understanding PythonURI

**PythonURI** is a variable in my frontend that references the URL `melodymates.stu.nighthawkcodingsociety.com`. It helps direct traffic correctly.

Flow: `8887 → 8404`

The URI (Uniform Resource Identifier) serves as an endpoint (a URL) to access resources.