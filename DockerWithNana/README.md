
```
[~]# docker -v
Docker version 20.10.23, build 7155243
[~]# docker run hello-world
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

[~]# docker images
REPOSITORY    TAG       IMAGE ID       CREATED         SIZE
hello-world   latest    feb5d9fea6a5   16 months ago   13.3kB
[~]# docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
[~]# docker ps -a
CONTAINER ID   IMAGE         COMMAND    CREATED          STATUS                      PORTS     NAMES
edba7dea412c   hello-world   "/hello"   11 seconds ago   Exited (0) 11 seconds ago             exciting_fermi
```

Pull download the images, but does not create any container
```
[~]# docker pull redis
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
[~]# docker images
REPOSITORY    TAG       IMAGE ID       CREATED         SIZE
redis         latest    19c51d4327cf   10 days ago     117MB
hello-world   latest    feb5d9fea6a5   16 months ago   13.3kB
```
Run command starts a container based on a image. Run command is basically combination of `pull` and `start` command.

```
[~]# docker run redis
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
[~]# docker ps
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS          PORTS      NAMES
4e9123593a90   redis     "docker-entrypoint.s…"   48 seconds ago   Up 48 seconds   6379/tcp   sharp_elgamal
[~]# docker ps -a
CONTAINER ID   IMAGE         COMMAND                  CREATED          STATUS                     PORTS      NAMES
4e9123593a90   redis         "docker-entrypoint.s…"   54 seconds ago   Up 54 seconds              6379/tcp   sharp_elgamal
edba7dea412c   hello-world   "/hello"                 9 minutes ago    Exited (0) 9 minutes ago              exciting_fermi
[~]# 

```

If we press ctl-C then the container will stop
```
[~]# docker run redis
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
[~]# docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
[~]# 
```


To run a container in detached mode pass param `-d`
```
[~]# docker run -d redis
d8c76648931fe572a4b8e863135716faf85b16a09cc0bb33c6722b7293e24a24
[~]# docker ps
CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS         PORTS      NAMES
d8c76648931f   redis     "docker-entrypoint.s…"   3 seconds ago   Up 3 seconds   6379/tcp   festive_yalow
[~]# docker stop d8c7
d8c7
[~]# docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
[~]# 

```

`docker run <image_name>` will run multiple container from same images.
`docker run <container_name>/<container_id>` will run already stopped container.

```
CONTAINER ID   IMAGE         COMMAND    CREATED          STATUS                      PORTS     NAMES
edba7dea412c   hello-world   "/hello"   30 minutes ago   Exited (0) 30 minutes ago             exciting_fermi
[~]# docker run -d redis
a0d9a783bc30e966575147c89cb3fad071252159cf8d6ce2b89387aea9d1a5d5
[~]# docker ps
CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS         PORTS      NAMES
a0d9a783bc30   redis     "docker-entrypoint.s…"   6 seconds ago   Up 5 seconds   6379/tcp   focused_shirley
[~]# docker stop focused_shirley 
focused_shirley
[~]# docker ps -a
CONTAINER ID   IMAGE         COMMAND                  CREATED          STATUS                      PORTS     NAMES
a0d9a783bc30   redis         "docker-entrypoint.s…"   16 seconds ago   Exited (0) 5 seconds ago              focused_shirley
edba7dea412c   hello-world   "/hello"                 30 minutes ago   Exited (0) 30 minutes ago             exciting_fermi
[~]# docker start focused_shirley 
focused_shirley
[~]# docker ps 
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS         PORTS      NAMES
a0d9a783bc30   redis     "docker-entrypoint.s…"   26 seconds ago   Up 2 seconds   6379/tcp   focused_shirley

```

Port binding
```
[~]# docker run -p 6000:6379 -d redis 
d7ec2faee3348d3980a4008acf6c08e76cdf27cf78b16cec4ec872c25b026f38
[~]# docker ps -a
CONTAINER ID   IMAGE         COMMAND                  CREATED             STATUS                      PORTS                                       NAMES
d7ec2faee334   redis         "docker-entrypoint.s…"   5 seconds ago       Up 4 seconds                0.0.0.0:6000->6379/tcp, :::6000->6379/tcp   dazzling_blackwell
a0d9a783bc30   redis         "docker-entrypoint.s…"   About an hour ago   Exited (0) 52 seconds ago                                               focused_shirley
edba7dea412c   hello-world   "/hello"                 2 hours ago         Exited (0) 2 hours ago                                                  exciting_fermi

```


Monitor logs with `log` command:

```
[~]# docker ps 
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS          PORTS                                       NAMES
d7ec2faee334   redis     "docker-entrypoint.s…"   10 minutes ago   Up 10 minutes   0.0.0.0:6000->6379/tcp, :::6000->6379/tcp   dazzling_blackwell
[~]# docker logs dazzling_blackwell 
1:C 28 Jan 2023 14:14:17.882 # oO0OoO0OoO0Oo Redis is starting oO0OoO0OoO0Oo
1:C 28 Jan 2023 14:14:17.882 # Redis version=7.0.8, bits=64, commit=00000000, modified=0, pid=1, just started
1:C 28 Jan 2023 14:14:17.882 # Warning: no config file specified, using the default config. In order to specify a config file use redis-server /path/to/redis.conf
1:M 28 Jan 2023 14:14:17.882 * monotonic clock: POSIX clock_gettime
1:M 28 Jan 2023 14:14:17.883 * Running mode=standalone, port=6379.
1:M 28 Jan 2023 14:14:17.883 # Server initialized
1:M 28 Jan 2023 14:14:17.883 # WARNING Memory overcommit must be enabled! Without it, a background save or replication may fail under low memory condition. Being disabled, it can can also cause failures without low memory condition, see https://github.com/jemalloc/jemalloc/issues/1328. To fix this issue add 'vm.overcommit_memory = 1' to /etc/sysctl.conf and then reboot or run the command 'sysctl vm.overcommit_memory=1' for this to take effect.
1:M 28 Jan 2023 14:14:17.883 * Ready to accept connections
[~]# docker logs -f dazzling_blackwell
1:C 28 Jan 2023 14:14:17.882 # oO0OoO0OoO0Oo Redis is starting oO0OoO0OoO0Oo
1:C 28 Jan 2023 14:14:17.882 # Redis version=7.0.8, bits=64, commit=00000000, modified=0, pid=1, just started
1:C 28 Jan 2023 14:14:17.882 # Warning: no config file specified, using the default config. In order to specify a config file use redis-server /path/to/redis.conf
1:M 28 Jan 2023 14:14:17.882 * monotonic clock: POSIX clock_gettime
1:M 28 Jan 2023 14:14:17.883 * Running mode=standalone, port=6379.
1:M 28 Jan 2023 14:14:17.883 # Server initialized
1:M 28 Jan 2023 14:14:17.883 # WARNING Memory overcommit must be enabled! Without it, a background save or replication may fail under low memory condition. Being disabled, it can can also cause failures without low memory condition, see https://github.com/jemalloc/jemalloc/issues/1328. To fix this issue add 'vm.overcommit_memory = 1' to /etc/sysctl.conf and then reboot or run the command 'sysctl vm.overcommit_memory=1' for this to take effect.
1:M 28 Jan 2023 14:14:17.883 * Ready to accept connections
^C⏎
```


interactive terminal mode
```
[~]# docker exec -it dazzling_blackwell /bin/bash
root@d7ec2faee334:/data# whoami
root
root@d7ec2faee334:/data# pwd
/data
root@d7ec2faee334:/data# ls
root@d7ec2faee334:/data# env
HOSTNAME=d7ec2faee334
REDIS_DOWNLOAD_SHA=06a339e491306783dcf55b97f15a5dbcbdc01ccbde6dc23027c475cab735e914
PWD=/data
HOME=/root
REDIS_VERSION=7.0.8
GOSU_VERSION=1.14
TERM=xterm
REDIS_DOWNLOAD_URL=http://download.redis.io/releases/redis-7.0.8.tar.gz
SHLVL=1
PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
_=/usr/bin/env
root@d7ec2faee334:/data# exit
exit
[~]# 
```

Network, a network named 'mongo-network' is created.
```

[~]# docker network ls
NETWORK ID     NAME         DRIVER    SCOPE
4791102ea737   bridge       bridge    local
6c7a9eb178e2   envize_net   bridge    local
75ba4091f70d   host         host      local
dcb53e65d7c2   none         null      local
[~]# docker network rm envize_net 
envize_net
[~]# docker network ls
NETWORK ID     NAME      DRIVER    SCOPE
4791102ea737   bridge    bridge    local
75ba4091f70d   host      host      local
dcb53e65d7c2   none      null      local
[~]# docker network create mongo-network
4ab8774504e758081da2590b8826851dd6108c0b68084424a8d695bbe1c443df
[~]# docker network ls
NETWORK ID     NAME            DRIVER    SCOPE
4791102ea737   bridge          bridge    local
75ba4091f70d   host            host      local
4ab8774504e7   mongo-network   bridge    local
dcb53e65d7c2   none            null      local
```

Run mongo and mongo express with a custom network named 'mongo-network'

```
[~]# docker pull mongo 
Using default tag: latest
latest: Pulling from library/mongo
846c0b181fff: Pull complete 
ef773e84b43a: Pull complete 
2bfad1efb664: Pull complete 
84e59a6d63c9: Pull complete 
d2f00ac700e0: Pull complete 
96d33bf42f45: Pull complete 
ebaa69d77b61: Pull complete 
f4af9408cbac: Pull complete 
70f9fc9ff713: Pull complete 
Digest: sha256:5b3815ec21a1dfd9f216ee83b324a0a779e1dfd17892e2f858e3c571f5980561
Status: Downloaded newer image for mongo:latest
docker.io/library/mongo:latest

```

```
[~]# docker run -d --net mongo-network --name mongodb \
                               -p 27017:27017 \
                               -e MONGO_INITDB_ROOT_USERNAME=admin \
                               -e MONGO_INITDB_ROOT_PASSWORD=password \
                               mongo
b86d7b1266ff098ba3e1783e9a03862d89268d48f658b0961959b236b08b2838
[~]# docker logs mongodb
about to fork child process, waiting until server is ready for connections.
forked process: 27

{"t":{"$date":"2023-01-28T17:08:50.725+00:00"},"s":"I",  "c":"CONTROL",  "id":20698,   "ctx":"-","msg":"***** SERVER RESTARTED *****"}
{"t":{"$date":"2023-01-28T17:08:50.726+00:00"},"s":"I",  "c":"NETWORK",  "id":4915701, "ctx":"-","msg":"Initialized wire specification","attr":{"spec":{"incomingExternalClient":{"minWireVersion":0,"maxWireVersion":17},"incomingInternalClient":{"minWireVersion":0,"maxWireVersion":17},"outgoing":{"minWireVersion":6,"maxWireVersion":17},"isInternalClient":true}}}
{"t":{"$date":"2023-01-28T17:08:50.729+00:00"},"s":"I",  "c":"CONTROL",  "id":23285,   "ctx":"main","msg":"Automatically disabling TLS 1.0, to force-enable TLS 1.0 specify --sslDisabledProtocols 'none'"}
{"t":{"$date":"2023-01-28T17:08:50.730+00:00"},"s":"I",  "c":"NETWORK",  "id":4648601, "ctx":"main","msg":"Implicit TCP FastOpen unavailable. If TCP FastOpen is required, set tcpFastOpenServer, tcpFastOpenClient, and tcpFastOpenQueueSize."}

```


Now start mongo express with the same network
```
[~]# docker run -d \
                                     -p 8081:8081 \
                                     -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin \
                                     -e ME_CONFIG_MONGODB_ADMINPASSWORD=password \
                                     --net mongo-network \
                                     --name mongo-express \
                                     -e ME_CONFIG_MONGODB_SERVER=mongodb \
                                     mongo-express
Unable to find image 'mongo-express:latest' locally
latest: Pulling from library/mongo-express
6a428f9f83b0: Pull complete
f2b1fb32259e: Pull complete
40888f2a0a1f: Pull complete
4e3cc9ce09be: Pull complete
eaa1898f3899: Pull complete
ab4078090382: Pull complete
ae780a42c79e: Pull complete
e60224d64a04: Pull complete
Digest: sha256:dcfcf89bf91238ff129469a5a94523b3025913dcc41597d72d4d5f4a0339cc7d
Status: Downloaded newer image for mongo-express:latest
6592c8324561458a8f58bd5f8b1747d72c637b9e97c27906194987bea940dd8e
[~]# docker ps
CONTAINER ID   IMAGE           COMMAND                  CREATED          STATUS          PORTS                                           NAMES
6592c8324561   mongo-express   "tini -- /docker-ent…"   7 minutes ago    Up 7 minutes    0.0.0.0:8081->8081/tcp, :::8081->8081/tcp       mongo-express
b86d7b1266ff   mongo           "docker-entrypoint.s…"   26 minutes ago   Up 26 minutes   0.0.0.0:27017->27017/tcp, :::27017->27017/tcp   mongodb
[~]# docker logs mongo-express
Welcome to mongo-express
------------------------


(node:6) [MONGODB DRIVER] Warning: Current Server Discovery and Monitoring engine is deprecated, and will be removed in a future version. To use the new Server Discover and Monitoring engine, pass option { useUnifiedTopology: true } to the MongoClient constructor.
Mongo Express server listening at http://0.0.0.0:8081
Server is open to allow connections from anyone (0.0.0.0)
basicAuth credentials are "admin:pass", it is recommended you change this in your config.js!
[~]#

```
