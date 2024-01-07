## Run this project

```sh
docker-compose up -d
```

## Build this project images

```sh
docker-compose build
```

## Find initial admin password

```sh
docker exec -it jenkins-practice_jenkins-server_1 cat /var/jenkins_home/secrets/initialAdminPassword
```