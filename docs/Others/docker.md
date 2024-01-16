Docker packs all your excutable code along with its util functions and many more. It is a complete package. This package is called a container. This container can be moved to any application, tools, software, package since it has all that needs to run an end-to-end appliations.

This Container itself is an Environment that all a Application needs to run on any machine.

This containerization & advantage of using this whole package any system, avoids the problem of "it runs in my machine, I am not sure why it is not running..".

This Container builds on top of a small base environment i.e called an Image. Users can add many other dependencies or packages on top of a base environment/Image.

- Dockerfile:
To build the container you need a Dockerfile. It is a text file with a set of instructions used to build a Docker image. 

- Docker-compose.yml:
A docker-compose.yml file is used to define and manage multi-container Docker applications. we can add multiple containers here. It is a YAML file that allows you to specify multiple services, their configurations, networks, volumes, and dependencies in a single file. Some key components of a docker-compose.yml file include:

```
version: '3.8'

services:
  web:
    image: nginx:latest
    ports:
      - "80:80"
    volumes:
      - ./nginx.conf:/etc/nginx/nginx.conf:ro
    depends_on:
      - api

  api:
    image: node:14
    working_dir: /usr/src/app
    volumes:
      - ./api:/usr/src/app
    command: npm start
```
