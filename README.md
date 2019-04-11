Docker Tutorial
=============

# List Docker CLI commands
docker
docker container --help

# Display Docker version and info
docker --version
docker version
docker info

#### Execute Docker image
docker run hello-world

#### List Docker images
docker image ls

#### List Docker containers (running, all, all in quiet mode)
docker container ls
docker container ls --all
docker container ls -aq

#### Define a container with Dockerfile
#### create Dockerfile
<pre><code>
#### Use an official Python runtime as a parent image
FROM python:2.7-slim

#### Set the working directory to /app
WORKDIR /app

#### Copy the current directory contents into the container at /app
COPY . /app

#### Install any needed packages specified in requirements.txt
RUN pip install --trusted-host pypi.python.org -r requirements.txt

#### Make port 80 available to the world outside this container
EXPOSE 80

#### Define environment variable
ENV NAME World

#### Run app.py when the container launches
CMD ["python", "app.py"]
</code></pre>
