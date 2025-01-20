# Docker

## Overview

Docker is an open platform for developing, shipping, and running applications. It enables you to separate your applications from your infrastructure so you can deliver software quickly. With Docker, you can manage your infrastructure in the same ways you manage your applications.

## Installation and Setup

1. **Install Docker**: Follow the instructions on the [official Docker website](https://docs.docker.com/get-docker/) to install Docker on your operating system.
2. **Verify Installation**: Open a terminal and type `docker --version` to verify the installation.

## Simple Example Using Docker

Here is a simple example of how to create and run a Docker container:

1. **Create a Dockerfile**: Create a file named `Dockerfile` with the following content:
   ```Dockerfile
   # Use an official Python runtime as a parent image
   FROM python:3.8-slim

   # Set the working directory in the container
   WORKDIR /app

   # Copy the current directory contents into the container at /app
   COPY . /app

   # Install any needed packages specified in requirements.txt
   RUN pip install --no-cache-dir -r requirements.txt

   # Make port 80 available to the world outside this container
   EXPOSE 80

   # Define environment variable
   ENV NAME World

   # Run app.py when the container launches
   CMD ["python", "app.py"]
   ```

2. **Build the Docker Image**: Open a terminal and navigate to the directory containing the Dockerfile. Run the following command to build the Docker image:
   ```sh
   docker build -t my-python-app .
   ```

3. **Run the Docker Container**: Run the following command to create and start a Docker container from the image:
   ```sh
   docker run -p 4000:80 my-python-app
   ```

4. **Access the Application**: Open a web browser and navigate to `http://localhost:4000` to see the application running inside the Docker container.

## Key Features and Common Use Cases

- **Containerization**: Docker allows you to package and run applications in isolated containers.
- **Portability**: Docker containers can run on any system that supports Docker, making it easy to move applications between environments.
- **Scalability**: Docker makes it easy to scale applications by running multiple containers.
- **Microservices**: Docker is commonly used to build and deploy microservices architectures.

## Official Documentation

For more information, visit the [official Docker documentation](https://docs.docker.com/).
