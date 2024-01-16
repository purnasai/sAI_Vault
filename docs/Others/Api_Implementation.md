Fast api
flask
Docker Gradio here: https://modelz.ai/blog/gradio-docker


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



#### Ports:
*127.0.0.1*: This is the specific numerical IP address of the loopback interface. It also refers to the local machine itself. Similar to `localhost`, a service set to listen on 127.0.0.1 is only reachable from the same machine where it's running.

*0.0.0.0*: When a service is set to listen on 0.0.0.0, it means it's binding to all available network interfaces on the machine. It allows the service to be accessible from any IP address associated with the host machine, including connections from the local machine (localhost/127.0.0.1) and external devices on the network.


#### Custom Domain:
using Nginx

https://mblog.com/https-custom-domain-with-mkcert

