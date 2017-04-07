# jenkins
This repository is docker of jenkins.


## Example of docker-compose.yml
```
version: '2'
services:
  jenkins:
    image: shu65/jenkins
    restart: always
    ports:
      - 8080:8080
    volumes:
      - ./jenkins_home:/var/jenkins_home
      - /var/run/docker.sock:/var/run/docker.sock
      - /usr/bin/docker:/usr/bin/docker
    environment:
      DOCKER_SOCKET: /var/run/docker.sock
      DOCKER_GROUP: dockerhost
      JENKINS_USER: jenkins
      DOCKER_HOST: unix:///var/run/docker.sock
```
