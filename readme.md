## Docker

1. #### Docker Important commands
    - for all docker containers **docker ps -a**
    - for all running docker containers **docker ps**
    - to run docker container **docker run image_name**
    - to run docker container in daemon **docker run -d image_name**
    - to map port use **docker -p port:port**
    - to check logs **docker logs -f container_id**
    - to add environment: use -e var:var-name
    - To include volume: (mongo db)
        - add -v and /to/path/:data/db
    - To commit the container: **docker commit container repository:tag**
      
2. #### Networking
    - creating network between docker-compose and external client 
        - **docker network create networkName**
        - **docker network connect --alias db networkName containerName**
    - Add this inside docker-compose
    - ```
          dbnet:
              external: 
                  name: networkName
      ```
3. #### House Keeping
    - Kill all running containers: **docker kill $(docker ps -q)**
    - Delete all stopped containers: **docker rm $(docker ps -a -q)**
    - Remove a docker image: **docker rmi image-name**
    - Delete untagged images: **docker rmi $(docker images -q -f dangling=true)**
    - Delete all images: **docker rmi $(docker images -q)**
    - **docker volume rm $(docker volume ls -f dangling=true -q)**
    
4. #### Compact vhdx in windows
    - cd C:\Users\UbaidurRehman\AppData\Local\Docker\wsl\data
    - Optimize-VHD .\ext4.vhdx -Mode Full

5.  #### Logs
    - Check the logs of container: docker logs container_name
    - Tail the logs of container: docker logs -f container_name

6. #### Execute the shell of the container
    - docker exec -it container-name bash

7. #### Building Image from docker file:
    - docker build -t tag-name

8. #### Fabric 8 Plugin
    - mvn clean package docker:build
    - mvn clean package docker:build docker:push

9. #### Storing docker id and password in maven settings
    - right click on the blank screen and hit create maven settings or edit settings
    - now add servers->server->id, username, password
    
10. #### CentOS and Ubuntu to run
    - docker run -d `ubuntu or centos` tail -f /dev/null
    - ps -ef ~used to list the commands

11. #### Ubuntu Stuff
    - docker create -v /tmp --name datacontainer ubuntu (create volume container)
    - docker run -t -i --volumes-from datacontainer ubuntu /bin/bash

12. #### Notes
    - Use relative path in windows
