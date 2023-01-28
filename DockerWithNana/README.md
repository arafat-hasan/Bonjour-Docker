
```
arafat_hasan@arafat-dsi ~/W/p/B/DockerWithNana (develop)> docker -v
Docker version 20.10.23, build 7155243
arafat_hasan@arafat-dsi ~/W/p/B/DockerWithNana (develop)> docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
2db29710123e: Pull complete
Digest: sha256:aa0cc8055b82dc2509bed2e19b275c8f463506616377219d9642221ab53cf9fe
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/

arafat_hasan@arafat-dsi ~/W/p/B/DockerWithNana (develop)> docker images
REPOSITORY    TAG       IMAGE ID       CREATED         SIZE
hello-world   latest    feb5d9fea6a5   16 months ago   13.3kB
arafat_hasan@arafat-dsi ~/W/p/B/DockerWithNana (develop)> docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
arafat_hasan@arafat-dsi ~/W/p/B/DockerWithNana (develop)> docker ps -a
CONTAINER ID   IMAGE         COMMAND    CREATED          STATUS                      PORTS     NAMES
edba7dea412c   hello-world   "/hello"   11 seconds ago   Exited (0) 11 seconds ago             exciting_fermi
```

Pull download the images, but does not create any container
```
arafat_hasan@arafat-dsi ~/W/p/B/DockerWithNana (develop)> docker pull redis
Using default tag: latest
latest: Pulling from library/redis
8740c948ffd4: Pull complete 
a2271c958e57: Pull complete 
495af11a3eac: Pull complete 
18b045ddb54d: Pull complete 
f49c2d6d086c: Pull complete 
14ed0c386119: Pull complete 
Digest: sha256:325d5a448d8f6c1d30a0a0fb26090343279d4cf23258b26b1745862f332e9479
Status: Downloaded newer image for redis:latest
docker.io/library/redis:latest
arafat_hasan@arafat-dsi ~/W/p/B/DockerWithNana (develop)> docker images
REPOSITORY    TAG       IMAGE ID       CREATED         SIZE
redis         latest    19c51d4327cf   10 days ago     117MB
hello-world   latest    feb5d9fea6a5   16 months ago   13.3kB
```
Run command starts a container based on a image

```
arafat_hasan@arafat-dsi ~/W/p/B/DockerWithNana (develop)> docker run redis
1:C 28 Jan 2023 12:35:01.423 # oO0OoO0OoO0Oo Redis is starting oO0OoO0OoO0Oo
1:C 28 Jan 2023 12:35:01.423 # Redis version=7.0.8, bits=64, commit=00000000, modified=0, pid=1, just started
1:C 28 Jan 2023 12:35:01.423 # Warning: no config file specified, using the default config. In order to specify a config file use redis-server /path/to/redis.conf
1:M 28 Jan 2023 12:35:01.423 * monotonic clock: POSIX clock_gettime
1:M 28 Jan 2023 12:35:01.423 * Running mode=standalone, port=6379.
1:M 28 Jan 2023 12:35:01.423 # Server initialized
1:M 28 Jan 2023 12:35:01.423 # WARNING Memory overcommit must be enabled! Without it, a background save or replication may fail under low memory condition. Being disabled, it can can also cause failures without low memory condition, see https://github.com/jemalloc/jemalloc/issues/1328. To fix this issue add 'vm.overcommit_memory = 1' to /etc/sysctl.conf and then reboot or run the command 'sysctl vm.overcommit_memory=1' for this to take effect.
1:M 28 Jan 2023 12:35:01.424 * Ready to accept connections

```
Now redis is running. Now open a new tab and check the status column.

```
arafat_hasan@arafat-dsi ~/W/p/B/DockerWithNana (develop)> docker ps
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS          PORTS      NAMES
4e9123593a90   redis     "docker-entrypoint.s…"   48 seconds ago   Up 48 seconds   6379/tcp   sharp_elgamal
arafat_hasan@arafat-dsi ~/W/p/B/DockerWithNana (develop)> docker ps -a
CONTAINER ID   IMAGE         COMMAND                  CREATED          STATUS                     PORTS      NAMES
4e9123593a90   redis         "docker-entrypoint.s…"   54 seconds ago   Up 54 seconds              6379/tcp   sharp_elgamal
edba7dea412c   hello-world   "/hello"                 9 minutes ago    Exited (0) 9 minutes ago              exciting_fermi
arafat_hasan@arafat-dsi ~/W/p/B/DockerWithNana (develop)> 

```

If we press ctl-C then the container will stop
```
arafat_hasan@arafat-dsi ~/W/p/B/DockerWithNana (develop)> docker run redis
1:C 28 Jan 2023 12:35:01.423 # oO0OoO0OoO0Oo Redis is starting oO0OoO0OoO0Oo
1:C 28 Jan 2023 12:35:01.423 # Redis version=7.0.8, bits=64, commit=00000000, modified=0, pid=1, just started
1:C 28 Jan 2023 12:35:01.423 # Warning: no config file specified, using the default config. In order to specify a config file use redis-server /path/to/redis.conf
1:M 28 Jan 2023 12:35:01.423 * monotonic clock: POSIX clock_gettime
1:M 28 Jan 2023 12:35:01.423 * Running mode=standalone, port=6379.
1:M 28 Jan 2023 12:35:01.423 # Server initialized
1:M 28 Jan 2023 12:35:01.423 # WARNING Memory overcommit must be enabled! Without it, a background save or replication may fail under low memory condition. Being disabled, it can can also cause failures without low memory condition, see https://github.com/jemalloc/jemalloc/issues/1328. To fix this issue add 'vm.overcommit_memory = 1' to /etc/sysctl.conf and then reboot or run the command 'sysctl vm.overcommit_memory=1' for this to take effect.
1:M 28 Jan 2023 12:35:01.424 * Ready to accept connections
^C1:signal-handler (1674910176) Received SIGINT scheduling shutdown...
1:M 28 Jan 2023 12:49:36.676 # User requested shutdown...
1:M 28 Jan 2023 12:49:36.676 * Saving the final RDB snapshot before exiting.
1:M 28 Jan 2023 12:49:36.678 * DB saved on disk
1:M 28 Jan 2023 12:49:36.678 # Redis is now ready to exit, bye bye...
arafat_hasan@arafat-dsi ~/W/p/B/DockerWithNana (develop)> docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
arafat_hasan@arafat-dsi ~/W/p/B/DockerWithNana (develop)> 
```


To run a container in detached mode pass param `-d`
```
arafat_hasan@arafat-dsi ~/W/p/B/DockerWithNana (develop)> docker run -d redis
d8c76648931fe572a4b8e863135716faf85b16a09cc0bb33c6722b7293e24a24
arafat_hasan@arafat-dsi ~/W/p/B/DockerWithNana (develop)> docker ps
CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS         PORTS      NAMES
d8c76648931f   redis     "docker-entrypoint.s…"   3 seconds ago   Up 3 seconds   6379/tcp   festive_yalow
arafat_hasan@arafat-dsi ~/W/p/B/DockerWithNana (develop)> docker stop d8c7
d8c7
arafat_hasan@arafat-dsi ~/W/p/B/DockerWithNana (develop)> docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
arafat_hasan@arafat-dsi ~/W/p/B/DockerWithNana (develop)> 

```

`docker run <image_name> will run multiple container from same images.
`docker run <container_name>/<container_id>` will run already stopped container.

```
CONTAINER ID   IMAGE         COMMAND    CREATED          STATUS                      PORTS     NAMES
edba7dea412c   hello-world   "/hello"   30 minutes ago   Exited (0) 30 minutes ago             exciting_fermi
arafat_hasan@arafat-dsi ~/W/p/B/DockerWithNana (develop)> docker run -d redis
a0d9a783bc30e966575147c89cb3fad071252159cf8d6ce2b89387aea9d1a5d5
arafat_hasan@arafat-dsi ~/W/p/B/DockerWithNana (develop)> docker ps
CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS         PORTS      NAMES
a0d9a783bc30   redis     "docker-entrypoint.s…"   6 seconds ago   Up 5 seconds   6379/tcp   focused_shirley
arafat_hasan@arafat-dsi ~/W/p/B/DockerWithNana (develop)> docker stop focused_shirley 
focused_shirley
arafat_hasan@arafat-dsi ~/W/p/B/DockerWithNana (develop)> docker ps -a
CONTAINER ID   IMAGE         COMMAND                  CREATED          STATUS                      PORTS     NAMES
a0d9a783bc30   redis         "docker-entrypoint.s…"   16 seconds ago   Exited (0) 5 seconds ago              focused_shirley
edba7dea412c   hello-world   "/hello"                 30 minutes ago   Exited (0) 30 minutes ago             exciting_fermi
arafat_hasan@arafat-dsi ~/W/p/B/DockerWithNana (develop)> docker start focused_shirley 
focused_shirley
arafat_hasan@arafat-dsi ~/W/p/B/DockerWithNana (develop)> docker ps 
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS         PORTS      NAMES
a0d9a783bc30   redis     "docker-entrypoint.s…"   26 seconds ago   Up 2 seconds   6379/tcp   focused_shirley

```

Port binding
```
arafat_hasan@arafat-dsi ~/W/p/B/DockerWithNana (develop)> docker run -p 6000:6379 -d redis 
d7ec2faee3348d3980a4008acf6c08e76cdf27cf78b16cec4ec872c25b026f38
arafat_hasan@arafat-dsi ~/W/p/B/DockerWithNana (develop)> docker ps -a
CONTAINER ID   IMAGE         COMMAND                  CREATED             STATUS                      PORTS                                       NAMES
d7ec2faee334   redis         "docker-entrypoint.s…"   5 seconds ago       Up 4 seconds                0.0.0.0:6000->6379/tcp, :::6000->6379/tcp   dazzling_blackwell
a0d9a783bc30   redis         "docker-entrypoint.s…"   About an hour ago   Exited (0) 52 seconds ago                                               focused_shirley
edba7dea412c   hello-world   "/hello"                 2 hours ago         Exited (0) 2 hours ago                                                  exciting_fermi

```
