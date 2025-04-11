

###  `docker ps`
**Purpose:** Lists all running containers.  

**Command:**
```bash
docker ps
```
output
CONTAINER ID   IMAGE     COMMAND              CREATED              STATUS              PORTS                  NAMES
563d4e88da0b   httpd     "httpd-foreground"   About a minute ago   Up About a minute   0.0.0.0:8080->80/tcp   apache_container
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
output
PS C:\Users\AL REHMAN LAPTOP\Desktop\docker 2q> docker logs apache_container
AH00558: httpd: Could not reliably determine the server's fully qualified domain name, using 172.17.0.2. Set the 'ServerName' directive globally to suppress this message
AH00558: httpd: Could not reliably determine the server's fully qualified domain name, using 172.17.0.2. Set the 'ServerName' directive globally to suppress this message
[Thu Apr 10 20:01:56.362946 2025] [mpm_event:notice] [pid 1:tid 1] AH00489: Apache/2.4.63 (Unix) configured -- resuming normal operations
[Thu Apr 10 20:01:56.377473 2025] [core:notice] [pid 1:tid 1] AH00094: Command line: 'httpd -D FOREGROUND'
172.17.0.1 - - [10/Apr/2025:20:02:18 +0000] "GET / HTTP/1.1" 200 45
###  `docker inspect`
**Purpose:** Shows low-level details about the container.  
**Command:**
```bash
docker inspect apache_container
```
output
[
    {
        "Id": "563d4e88da0bdaf77b06ee3449cc9aa3c19fdcb6eda2c6fe8a4c16f8d5302f2c",
        "Created": "2025-04-10T20:01:54.861748412Z",
        "Path": "httpd-foreground",
        "Args": [],
        "State": {
            "Status": "running",
            "Running": true,
            "Paused": false,
            "Restarting": false,
            "OOMKilled": false,
            "Dead": false,
            "Pid": 1073,
            "ExitCode": 0,
            "Error": "",
            "StartedAt": "2025-04-10T20:01:55.12559656Z",
            "FinishedAt": "0001-01-01T00:00:00Z"
        },
        "Image": "sha256:4564ca7604957765bd2598e14134a1c6812067f0daddd7dc5a484431dd03832b",
        "ResolvConfPath": "/var/lib/docker/containers/563d4e88da0bdaf77b06ee3449cc9aa3c19fdcb6eda2c6fe8a4c16f8d5302f2c/resolv.conf",
        "HostnamePath": "/var/lib/docker/containers/563d4e88da0bdaf77b06ee3449cc9aa3c19fdcb6eda2c6fe8a4c16f8d5302f2c/hostname",
        "HostsPath": "/var/lib/docker/containers/563d4e88da0bdaf77b06ee3449cc9aa3c19fdcb6eda2c6fe8a4c16f8d5302f2c/hosts",
        "LogPath": "/var/lib/docker/containers/563d4e88da0bdaf77b06ee3449cc9aa3c19fdcb6eda2c6fe8a4c16f8d5302f2c/563d4e88da0bdaf77b06ee3449cc9aa3c19fdcb6eda2c6fe8a4c16f8d5302f2c-json.log",
        "Name": "/apache_container",
        "RestartCount": 0,
        "Driver": "overlayfs",
        "Platform": "linux",
        "MountLabel": "",
        "ProcessLabel": "",
        "AppArmorProfile": "",
        "ExecIDs": null,
        "HostConfig": {
            "Binds": null,
            "ContainerIDFile": "",
            "LogConfig": {
                "Type": "json-file",
                "Config": {}
            },
            "NetworkMode": "bridge",
            "PortBindings": {
                "80/tcp": [
                    {
                        "HostIp": "",
                        "HostPort": "8080"
                    }
                ]
            },
###  `docker exec`
**Purpose:** Runs a command inside the container (like opening bash shell).  
**Command:**
```bash
docker exec -it apache_container bash
```
output
CONTAINER ID   NAME      CPU %     MEM USAGE / LIMIT   MEM %     NET I/O   BLOCK I/O   PIDS
CONTAINER ID   NAME      CPU %     MEM USAGE / LIMIT   MEM %     NET I/O   BLOCK I/O   PIDS
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
output
CONTAINER ID   NAME              CPU %     MEM USAGE / LIMIT   NET I/O     BLOCK I/O
563d4e88da0b   httpd             0.15%       50MiB / 512MiB       2kB / 2kB 0B/
###  `docker top`
**Purpose:** Shows running processes in the container.  
**Command:**
```bash
docker top apache_container
```
output
UID       PID     CMD
root      1234    node app

###  `docker start`
**Purpose:** Starts a stopped container.  
**Command:**
```bash
docker start apache_container
```
output
apache_container

###  `docker pause` & `docker unpause`
**Purpose:** Pauses/unpauses all processes in container.  
**Command:**
```bash
docker pause apache_container
docker unpause apache_container
```
output
apache_container
apache_container
###  `docker rename`
**Purpose:** Renames the container.  
**Command:**
```bash
docker rename apache_container apache_web
```
apache_web

###  `docker wait`
**Purpose:** Waits until container exits, then returns exit code.  
**Command:**
```bash
docker wait apache_container
```
output
0


###  `docker port`
**Purpose:** Shows the port mapping of container.  
**Command:**
```bash
docker port apache_container
```
output
80/tcp -> 0.0.0.0:8080
###  `docker update`
**Purpose:** Updates resource limits (e.g., memory).  
**Command:**
```bash
docker update --memory 100m --memory-swap 100m apache_container
```
output
Error response from daemon: Cannot update container 563d4e88da0bdaf77b06ee3449cc9aa3c19fdcb6eda2c6fe8a4c16f8d5302f2c: Memory limit should be smaller than already set memoryswap limit, update the memoryswap at the same time

###  `docker restart`
**Purpose:** Restarts a container.  
**Command:**
```bash
docker restart apache_container
```
output

apache_web
