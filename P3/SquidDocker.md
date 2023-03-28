# Configuring Squid
For this project we opted to setup squid inside a docker container. The first image that we tried was the ubunut squid image, but the image was bugged and would not run so we had to use an alternate image. The image tath we opted to use was sameersbn/squid.

## Docker Compose
In the github repository for the docker image, there is a baseline docker-compose.yml file that we are going to use. The following were added to the file 
* `container_name: squid` to give the container a name when it runs
* `networks: - proxy` to seperate the network from other containers
* `ports: - 172.20.10.10:3128:3128` to forward the port clients will connect to to the correct ip on the host machine
* `volumes: - ./cache:/var/spool/squid` to keep the logs even if the container is down

## Running
To run the docker container we go to the same directory that the docker-compose.yaml file is in and run `docker compose up -d`.

![SquidDocker](https://user-images.githubusercontent.com/55543355/228108406-2a59e4d8-5dfb-4e0a-b36f-7dfb764119af.jpg)

## Web Browsing Test

![WebBrowsing](https://user-images.githubusercontent.com/55543355/228110702-f0b5ee29-caea-4045-9ecd-8e90b9458c7c.jpg)

## DNF Test

![DNFUpdates](https://user-images.githubusercontent.com/55543355/228111484-5d0866e5-9b54-4f68-84f0-d89da6a8d811.jpg)
