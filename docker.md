- see docker images
docker ps

- run notebook container
docker run -p 8888:8888 jupyter/scipy-notebook:b418b67c225b

- add volume for docker
docker run -v /Users/vadim/Desktop/docker:/home/jovyan/ -p 8888:8888 jupyter/scipy-notebook:b418b67c225b 

- get into container (NAMES -> ID)
docker exec -it ddf8f7d4f920 bash

- copy file to container (run from local machine, not docker)
docker cp wine.data 79d3b5ac7890:/home/jovyan/wine.data

- create Dockerfile and install librarires
docker build .

(copy id of image)

docker run -v /Users/vadim/Desktop/docker:/home/jovyan/ -p 8888:8888 d8085e532b49d4f0659985e85d866f3129d379a2d8cf3578ba6dc719a2a46d0d

- use alias(tag) instead of image has-id
docker build -t my_notebook .
docker run -v /Users/vadim/Desktop/docker:/home/jovyan/ -p 8888:8888 my_notebook

- docker compose
    - create docker-compose file
docker-compose up
docker-compose up --build

- docker + postgres
    - add postgres to docker-compose
    db:
        image: postgres
        restart: always