# Java Docker Application

This project demonstrates how to build and run a Java application using Docker.

## Prerequisites

- Docker installed on your machine [Docker](https://www.docker.com).
- Java Development Kit (JDK) installed [Java Development Kit](https://www.oracle.com/java/technologies/downloads/) (https://adoptium.net/temurin/releases/).

## Project Structure

## Dockerfile

Here is the `Dockerfile` used for this project:

```dockerfile
FROM openjdk:latest
WORKDIR /app
COPY . /app
RUN javac sample.java
CMD ["java", "sample"]
```

## Building and Running the Docker Image

Step 1: Compile the Java Program Locally

Before building the Docker image, ensure that your Java program compiles and runs correctly.

```bash
javac sample.java
java sample
```

Step 2: Build the Docker Image

To build the Docker image, navigate to the directory containing your Dockerfile and run the following command:

```bash
docker build -t myjavaapp .
```

Step 3: Run the Docker Container

To run the Docker container, use the following command:

```bash
docker run --name java1 myjavaapp
```

Step 4: Check Docker Containers and Images

To list all Docker images, use:

```bash
docker images
```

To list all Docker containers (including stopped ones), use:

```bash
docker ps -a
```

Step 5: Remove Docker Containers

To remove a Docker container, use the following command, replacing <container_id> with the actual container ID:

```bash
docker rm <container_id>
```

Step 6: Remove Docker Images

To remove a Docker image, use the following command, replacing <image_id> with the actual image ID:

```bash
docker rmi <image_id>
```

## Common Docker Commands

Build a Docker Image

```bash
docker build -t <image_name> .
```

Run a Docker Container

```bash
docker run --name <container_name> <image_name>
```

List Docker Images

```bash
docker images
```

List Docker Containers

```bash
docker ps -a
```

Remove a Docker Container

```bash
docker rm <container_id>
```

Remove a Docker Image

```bash
docker rmi <image_id>
```

## Example Commands

1. Build the Docker image:

```bash
docker build -t calci .
```

2. Run the Docker container interactively:

```bash
docker run --name calciapp calci
```

3. Remove a Docker container:

```bash
docker rm <container_id>
```

4.	List Docker images:

```bash
docker images
```

5.	List Docker containers:

```bash
docker ps -a
```

6.	Run the Docker container in detached mode:

```bash
docker run -it --name calciapp -d calci
```

7.	Execute a command in a running Docker container:

```bash
docker exec -it calciapp java sample
```