docker build  -t class1 .***class1 is the name of the image and by" ." we assign that the dockerfile is somewhere in this folder***
docker run class1
go into another terminal, bash for mine
sudo docker ps
sudo docker exec -it **first two digit of container id** sh
