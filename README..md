

###  `docker ps`
**Purpose:** Lists all running containers.  
**Command:**
```bash
docker ps
```
###  `docker stop`
**Purpose:** Stops the running container.  
**Command:**
```bash
docker stop apache_container
```

###  `docker rm`
**Purpose:** Removes the stopped container.  
**Command:**
```bash
docker rm apache_container
```
###  `docker logs`
**Purpose:** Shows logs of the container (useful for debugging).  
**Command:**
```bash
docker logs apache_container
```
###  `docker inspect`
**Purpose:** Shows low-level details about the container.  
**Command:**
```bash
docker inspect apache_container
```

###  `docker exec`
**Purpose:** Runs a command inside the container (like opening bash shell).  
**Command:**
```bash
docker exec -it apache_container bash
```

###  `docker attach`
**Purpose:** Attaches your terminal to a running container.  
**Command:**
```bash
docker attach apache_container
```

###  `docker commit`
**Purpose:** Creates a new image from current container.  
**Command:**
```bash
docker commit apache_container apache_custom
```

###  `docker cp`
**Purpose:** Copies file from container to host.  
**Command:**
```bash
docker cp apache_container:/usr/local/apache2/conf/httpd.conf ./httpd.conf
```

###  `docker stats`
**Purpose:** Shows real-time usage stats of containers.  
**Command:**
```bash
docker stats
```
###  `docker top`
**Purpose:** Shows running processes in the container.  
**Command:**
```bash
docker top apache_container
```

###  `docker start`
**Purpose:** Starts a stopped container.  
**Command:**
```bash
docker start apache_container
```


###  `docker pause` & `docker unpause`
**Purpose:** Pauses/unpauses all processes in container.  
**Command:**
```bash
docker pause apache_container
docker unpause apache_container
```
###  `docker rename`
**Purpose:** Renames the container.  
**Command:**
```bash
docker rename apache_container apache_web
```

###  `docker wait`
**Purpose:** Waits until container exits, then returns exit code.  
**Command:**
```bash
docker wait apache_container
```


###  `docker port`
**Purpose:** Shows the port mapping of container.  
**Command:**
```bash
docker port apache_container
```

###  `docker update`
**Purpose:** Updates resource limits (e.g., memory).  
**Command:**
```bash
docker update --memory 100m --memory-swap 100m apache_container
```

###  `docker restart`
**Purpose:** Restarts a container.  
**Command:**
```bash
docker restart apache_container
```


