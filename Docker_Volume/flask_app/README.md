# Flask App — AWS ECS Deployment

A minimal Flask web application built for learning containerization and deployment to **AWS ECS (Elastic Container Service)**.

## Features

- Responsive landing page with modern glassmorphism UI
- `/health` endpoint for ECS load balancer health checks
- Two Dockerfiles — simple and multistage (distroless)

## Project Structure

```
flask-app-ecs/
├── app.py                 # Flask app with routes
├── run.py                 # Entry point (host 0.0.0.0, port 80)
├── requirements.txt       # Python dependencies
├── templates/
│   └── index.html         # Landing page
├── Dockerfile             # Simple single-stage build
└── Dockerfile-multi       # Multistage build with distroless

************************************************************
docker pull mysql:latest
docker run -d -e MYSQL_ROOT_PASSWORD=root mysql:latest
docker exec -it containerid bash
mysql -u root -p
show databses;
create databse imp_data;
show databases;
exit
exit
docker stop containerid
docker start containerid
docker exec -it containerid bash
mysql -u root -p
show databases;
exit
exit
docker stop containerid && docker rm containerid

#now to check if imp_data exist or not.
docker run -d -e MYSQL_ROOT_PASSWORD=root mysql:latest
docker exec -it containerid bash
mysql -u root -p
show databses;
exit 
exit
#here imp_data is not visible


#Understanding Docker volume concept

docker volume ls
docker volume create mysql-data
docker volume ls
docker volume inspect mysql-data
docker run -d -v mysql-data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=root mysql:latest
#your mysql-data is now stored in the mysql-data volume, not inside the container

docker ps
docker exec -it cont bash
mysql -u root -p
create databse imp_data;
show databases;
exit
exit
docker stop containerid && docker rm containerid

#To verify

docker run -d -v mysql-data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=root mysql:latest
docker ps
docker exec -it cont bash
mysql -u root -p
show databases