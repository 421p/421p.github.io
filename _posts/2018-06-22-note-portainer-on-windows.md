---
published: true
title: '[Note] Portainer and Docker on Windows'
tags: portainer docker windows remote endpoint dockeronwindows
---

A quick instruction on how to run Portainer (Web UI for Docker) in a Docker on Windows (Linux containers, hyper-v, not LCOW)

##### 1) Create a loopback redirection

On some Windows setup, Docker is listening on the local loopback address and cannot be accessed from within the Portainer container. You can use netsh to create a port redirection, and then use the newly created IP address to connect from Portainer.

```
netsh interface portproxy add v4tov4 listenaddress=10.0.75.1 listenport=2375 connectaddress=127.0.0.1 connectport=2375
```

##### 2) Create a volume for data persistence and run container

```
docker volume create portainer_data
docker run -d -p 9000:9000 --name portainer --restart always -v portainer_data:/data portainer/portainer
```

##### 3) Go to [http://localhost:9000](http://localhost:9000) and create admin account

![chrome_2018-06-22_23-02-08.jpg]({{site.baseurl}}/_posts/chrome_2018-06-22_23-02-08.jpg)

##### 4) Set up a remote endpoint with ip 10.0.75.1:2375

![chrome_2018-06-22_23-04-13.jpg]({{site.baseurl}}/_posts/chrome_2018-06-22_23-04-13.jpg)

##### 5) Done!
