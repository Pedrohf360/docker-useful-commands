# Covering:

Tutorial 1 link: https://www.youtube.com/watch?v=YFl2mCHdv24

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

#Tutorial 2: https://www.youtube.com/watch?v=IBvBUtHdku0

List existing containers and their status:
sudo docker ps -a

Current, tests works with: vigilant_heisenberg, id: ecaab994963b
sudo docker start (container ID)

Enter in container virtual machine:
sudo docker exec -it ecaab994963b "bash"

ls /opt/mssql-tools/bin/sqlcmd* -> see if exists sqlcmd

ln -sfn /opt/mssql-tools/bin/sqlcmd /usr/bin/sqlcmd -> turn on cmd

To login in sql server:
sqlcmd -S localhost -U SA -P "0A62YOUKNOWTHERESTBRO"

## SQL commands used:
```
1> SELECT name FROM masater.dbo.sysdatabases
2> go
Msg 208, Level 16, State 1, Server ecaab994963b, Line 1
Invalid object name 'masater.dbo.sysdatabases'.
1> SELECT name FROM master.dbo.sysdatabases
2> go
name                                                                                                                            
--------------------------------------------------------------------------------------------------------------------------------
master                                                                                                                          
tempdb                                                                                                                          
model                                                                                                                           
msdb                                                                                                                            

(4 rows affected)
1> CREATE DATABASE labInf
2> go
1> SELECT name FROM master.dbo.sysdatabases
2> go
name                                                                                                                            
--------------------------------------------------------------------------------------------------------------------------------
master                                                                                                                          
tempdb                                                                                                                          
model                                                                                                                           
msdb                                                                                                                            
labInf       
```
