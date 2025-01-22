# Docker Networking Tutorial (Bridge - None - Host - IPvlan)



### Bridge

```bash
docker network ls
docker network inspect bridge
docker run -d --name backend -p 8081:8080 dockernetworkimage
docker ps
docker inspect backend
curl localhost:8081/api/info

docker run -d --name frontend -p 8082:8080 dockernetworkimage
docker ps

curl localhost:8081/api/info
curl localhost:8082/api/info
docker exec -it backend sh

curl 172.17.0.2:8080/api/info
curl 172.17.0.3:8080/api/info

curl frontend:8080/api/info

docker rm -f backend frontend

docker network create my-bridge-net --subnet 10.0.0.0/19 --gateway 10.0.0.1
docker network ls
docker network inspect my-bridge-net

docker run -d --name backend -p 8081:8080 --network my-bridge-net dockernetworkimage
docker run -d --name frontend -p 8082:8080 --network my-bridge-net dockernetworkimage
curl localhost:8081/api/info
curl localhost:8082/api/info

docker exec -it backend sh
curl frontend:8080/api/info

docker rm -f backend frontend
docker network rm my-bridge-net

docker compose -f 1-compose.yaml up -d
```

### Host

```bash
docker run -d --name backend --network host dockernetworkimage
docker ps

curl 192.168.50.55:8080/api/info

docker rm -f backend
```

### None

```bash
docker run -d --name backend --network none dockernetworkimage
docker exec backend ip addr

docker run -d --name backend -p 8081:8080 --network none dockernetworkimage
docker run -d --name backend -p 8081:8080 dockernetworkimage
curl localhost:8081/api/info
```

## IPvlan

```bash
ip addr

docker network create -d ipvlan \
    --subnet=192.168.50.0/24 \
    --gateway=192.168.50.1 \
    -o ipvlan_mode=l2 \
    -o parent=ens33 my-ipvlan-net

docker network ls
docker run -d --name backend --network my-ipvlan-net dockernetworkimage
docker inspect backend

curl 192.168.50.2:8080/api/info
```

