## Docker Network
### Docker Network
A container can communicate with the internet. we can test it using `ping google.com`.  A docker container uses Host machines Network connectivity using a method called **BRIDGE** connectivity.

we can inspec the network details that is using **BRIDGE** connectivity.  use the command `docker network inspect bridge`. This is the default Network connectivity.

type `docker network ls` to see list of network drivers that docker generally communicates with.

```cmd
NETWORK ID     NAME      DRIVER    SCOPE
326d12796a29   bridge    bridge    local
627f5ee25ca3   host      host      local
952ace5dfb0a   none      null      local
```

### changing network driver.
By default a Docker container communicates with Outside network using Host network connectivity though **BRIDGE** connectivity method. 

We can externally change the **Connectivity method by chaning driver** with **--network=host** argument along with `docker run` argument.

#### No port mapping.
Since we changed the connectivity method to **host**, Docker container directly uses host network capabilities, so as a result **Port Mappping** is not required i.e, `docker run imagename:tag` instead of `docker run -p 3000:8000 imagename:tag`.

### Create New Networkdriver
we can create our own network driver using `docker network create -d bridge newnetworkname`. once we created this network driver, we can attach our container to this newly created driver. 

we can keep two container running through thie newly created network driver using commands like:

- container1 with `docker run --network=newnetworkname imagename:tag` and
- container2 with `docker run --network=newnetworkname imagename1:tag`.


## Volume Mounting:
when a container is destroyed, memory reserved for that container also gets destroyed. To avoid that we can use `docker volume` to setup/mount our Local folder to the Container. 

So all the files, folders, applications created in this folder in the container, reflects the same contents in the Local folder. This way even if our container is destroyed, contents in the Local folder stay same.

we can connect our local folder to/as the container folder using command `docker run -v localfolderpath:containerfolderpath imagename:tag`. 

Later when we want to connect this local folder to another container, then again we use `docker run -v localfolderpath:containerfolderpath imagename:tag`.



## Docker multi-stage builds:
This is also an interesting concept, that one should be familiar with. Note on it later. for now check the official documentation [here](https://docs.docker.com/build/building/multi-stage/)

