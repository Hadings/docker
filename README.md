Docker Tutorial
=============
URL "https://docs.docker.com/get-started/part2/"

#### List Docker CLI commands
<pre><code>
docker
docker container --help
</code></pre>
#### Display Docker version and info
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

#### Create two more files, requirements.txt and app.py
#### requirements.txt
<code><pre>
Flask
Redis
</code></pre>
#### app.py
```
from flask import Flask
from redis import Redis, RedisError
import os
import socket
# Connect to Redis
redis = Redis(host="redis", db=0, socket_connect_timeout=2, socket_timeout=2)

app = Flask(__name__)

@app.route("/")
def hello():
    try:
        visits = redis.incr("counter")
    except RedisError:
        visits = "<i>cannot connect to Redis, counter disabled</i>"

    html = "<h3>Hello {name}!</h3>" \
           "<b>Hostname:</b> {hostname}<br/>" \
           "<b>Visits:</b> {visits}"
    return html.format(name=os.getenv("NAME", "world"), hostname=socket.gethostname(), visits=visits)

if __name__ == "__main__":
    app.run(host='0.0.0.0', port=80)
```

