# Covering:

Tutorial link: https://www.youtube.com/watch?v=YFl2mCHdv24

1. What is Docker
2. Virtual Machines vs. Docker
3. Introduction to Dockerfiles, images and containers
4. The Docker Hub
5. Writing a Dockerfile
6. Building an image
7. Running a container
8. Mounting volumes
9. One process per container

useful commands:

sudo apt-get update
sudo apt-get install docker.io

sudo service docker start/stop


docker info


docker images
docker ps (optional "-a" flag) : list all running containers

docker run container-name : if container exists locally, get it. If not, pull from docker hub library.

docker build -t (project-name) (path)

docker run -p 80:80 hello-world
explanation: docker run -p hostPort:containerPort hello-world

during develop two types of volumes:

1) consist and share data between containers
2) share folders between host and containers


to mount local: docker run -p 80:80 -v /Documents/projects/about-docker/docker-test/src/:/var/www/html/ hello-world

