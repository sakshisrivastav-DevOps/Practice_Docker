#Docker creates virtual private network inside your machine for containers.
#Container names become hostnames inside same Docker network
docker network create networkpractice

#Lists all Docker virtual networks
docker network ls

#Build backend image from backend Dockerfile
docker build -t backend-app ./backend

#Build frontend image from frontend Dockerfile
docker build -t frontend-app ./frontend

#Flask app listens on port 5000 inside container
#Host port 5000 mapped to container port 5000
#Backend and frontend communicate internally using Docker network
docker run -d --name backend -p 5000:5000 --network=networkpractice backend-app

#nginx listens on port 80 inside container
#Host port 8080 mapped to container port 80
docker run -d --name frontend -p 8080:80 --network=networkpractice frontend-app

#Open shell inside running frontend container
docker exec -it frontendcontainerid bash

#Docker DNS resolves backend container name to container IP
ping backend

#If ping command not available
cat /etc/os-release

#If Debian/Ubuntu install ping utility
apt update && apt install -y iputils-ping

#Again ping backend container
ping backend

#Frontend container sends request internally to backend container
curl http://backend:5000

#Important
#localhost inside container means same container itself
#Containers communicate using container-name:port

#Browser Access
#Frontend -> http://localhost:8080
#Backend  -> http://localhost:5000


| Communication Type    | Uses           |
| --------------------- | -------------- |
| Browser → Container   | Port mapping   |
| Container → Container | Docker network |
