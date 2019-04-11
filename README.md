Docker Tutorial
=============

# List Docker CLI commands
<pre><code>
docker
docker container --help
</code></pre>
# Display Docker version and info
<pre><code>
docker --version
docker version
docker info
</code></pre>
#### Execute Docker image
<pre><code>
docker run hello-world
</code></pre>
#### List Docker images
<pre><code>
docker image ls
</code></pre>
#### List Docker containers (running, all, all in quiet mode)
<pre><code>
docker container ls
docker container ls --all
docker container ls -aq
</code></pre>
#### Define a container with Dockerfile
#### create Dockerfile
<pre><code>
# Use an official Python runtime as a parent image
FROM python:2.7-slim

# Set the working directory to /app
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install any needed packages specified in requirements.txt
RUN pip install --trusted-host pypi.python.org -r requirements.txt

# Make port 80 available to the world outside this container
EXPOSE 80

# Define environment variable
ENV NAME World

# Run app.py when the container launches
CMD ["python", "app.py"]
</code></pre>
