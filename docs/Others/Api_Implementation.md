REST API Framework:
- Fast api
- Flask
- Djano Rest Framework**

Containerization:
- Docker 
- Kubernetes

Quick build apps:
- Gradio here: https://modelz.ai/blog/gradio-docker
- streamlit

BackEnd tech:
- python(django, flask)
- node js
- go lang
- next js

FrontEnd tech:
- angular js
- react js
- next js**

API Development Testing tools:
- Insomnia
- postman

Project Design tool:
- figma - for ui screen design

**Database Management**: Understanding databases is crucial. Common ones include:
- **SQL databases**: Such as PostgreSQL, MySQL, SQLite
- **NoSQL databases**: Like MongoDB, Cassandra, Redis.

**Version Control System**:
- **Git**: Essential for code versioning, collaboration, and tracking changes


#### Curl
curl (short for "Client URL") is a command line tool that enables data transfer over various network protocols. 
Example curl command:

```
curl -X 'POST' \
  'http://localhost:5000/predict' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{"image_url":"https://images.pexels.com/photos/2071882/pexels-photo-2071882.jpeg?cs=srgb&dl=pexels-wojciech-kumpicki-2071882.jpg&fm=jpg"}'
```

Once you write the code in such a way, that they accept `get` and `post` requests using `Flask Routes` or `FastAPI Routes`, then we can run this File/application to serve requests.

To serve these applications thorugh requests (or) to start serving this File/application we need   `Gunicorn` or `uvicorn` like *Server Interfaces*.


- **Gunicorn**: is a `WSGI(Web Server Gateway Interface)` that handles requests to the application in a synchronous(one at a time) manner. Like a Single Lane road in Layman terms.

- **Uvicorn**: is a `ASGI(Asynchronous Server Gateway Interface)` that handles requests to the application in a Asynchronous(many at a time) manner. Like a Multi-lane road in Layman terms.

**NOTE:** Let's say both unicorn and gunicorn are for hosting a web server.

- **supervisor**: is used to manage & monitor a process, ensure they stay running like `docker` does.
 Let's say you have a Python script named `my_script.py` that needs to be constantly running as a background process.
 
 one need to create a `Configuration` file for that. sample one looks as below:
 ```ini
command=/usr/bin/python3 /path/to/my_script.py
autostart=true
autorestart=true
stderr_logfile=/var/log/my_script.err.log
stdout_logfile=/var/log/my_script.out.log
 ```

- **RQworker**: Rq (Redis Queue) is a Python library for queuing and processing tasks asynchronously.  They are to handle background job processing in a distributed system.
Example scenarios:
  - Handling tasks that can be performed asynchronously, such as sending emails or processing image uploads.
  - Running background jobs in a Flask or Django application to avoid blocking the main request-response cycle.

#### Ports:
*127.0.0.1*: This is the specific numerical IP address of the loopback interface. It also refers to the local machine itself. Similar to `localhost`, a service set to listen on 127.0.0.1 is only reachable from the same machine where it's running.

*0.0.0.0*: When a service is set to listen on 0.0.0.0, it means it's binding to all available network interfaces on the machine. It allows the service to be accessible from any IP address associated with the host machine, including connections from the local machine (localhost/127.0.0.1) and external devices on the network.

#### Static file Server
- **python -m http.server 8080**: is to serve static files. This is only suitable for Local development or Sharing files within your local network.
  Ex: if you want to serve files in your ec2 instance machine, then using the above would work. but running this in your local machine & if you want to serve these local files, then this wouldn't work.


#### NGrok:
- is a Tunneling service. It exposes local host servers to public internet. It allows you to temporarily expose a local server to the internet, which can be useful during development and testing.
  - sign up a free account.
  - install ngrok
  - `./ngrok http YOUR_PORT` 
  These are arbitrary steps. check internet for more.

#### Custom Domain:
using Nginx

**Ngrok/Nginx**: tools for networking and server configurations. Ngrok creates secure tunnels to local servers(localhost:8000 port), allowing access from the internet. Nginx is a web server that manages web traffic, handles reverse proxy, and serves web content efficiently.(**Serverconfiguration**)


https://mblog.com/https-custom-domain-with-mkcert

**Background Tasks**:
- **Celery (Python)**: Enables you to run asynchronous tasks and is commonly used for handling background jobs.

**Error Monitoring and Logging**:    
    - **Sentry, ELK Stack (Elasticsearch, Logstash, Kibana)**: Tools to monitor and log errors, system performance, and application behavior

**Caching**:    
    - **Redis**: Used as an in-memory data store for caching frequently accessed data, improving application performance.

**WebSockets** (for real-time communication):    
    - **Socket.io (for Node.js)**: Enables real-time bidirectional event-based communication

**Authentication and Authorization**:
- **JWT (JSON Web Tokens)**: For secure authentication
- **OAuth**: Authentication framework used for authorization


