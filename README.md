# Docker
Learn Docker Deep Dive

### How to run python "hello world" program using dockerfile and docker container?
To run a Python "Hello World" program using a Dockerfile and Docker container, follow these steps:

1. **Install Docker**: Ensure that Docker is installed on your system. You can download and install Docker from the official website (https://www.docker.com/get-started) if you haven't already.

2. **Create a Python "Hello World" Script**: Create a simple Python script that prints "Hello, World!" to the console. You can create a file named `hello.py` with the following content:

    ```python
    print("Hello, World!")
    ```

3. **Create a Dockerfile**: Create a Dockerfile to define the Docker image. You can use a text editor to create a file named `Dockerfile` (no file extension) with the following content:

    ```Dockerfile
    # Use an official Python runtime as a parent image
    FROM python:3.8-slim

    # Set the working directory to /app
    WORKDIR /app

    # Copy the current directory contents into the container at /app
    COPY . /app

    # Run hello.py when the container launches
    CMD ["python", "hello.py"]
    ```

    This Dockerfile uses the official Python image from Docker Hub and sets up a working directory (`/app`) where it copies the `hello.py` script. Finally, it specifies the command to run when the container starts.

4. **Build the Docker Image**: Open a terminal and navigate to the directory containing your `Dockerfile` and `hello.py`. Run the following command to build the Docker image:

    ```bash
    docker build -t hello-python .
    ```

    This command tells Docker to build an image tagged as "hello-python" using the current directory as the build context.

5. **Run the Docker Container**: Once the image is built, you can run a Docker container from it using the following command:

    ```bash
    docker run hello-python
    ```

    This command starts a new container based on the "hello-python" image, which executes the `hello.py` script, and you will see "Hello, World!" printed in the terminal.

### ---------------------------------------------------------------------------------------------
