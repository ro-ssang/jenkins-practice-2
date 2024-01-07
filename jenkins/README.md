## Create jenkins image

```sh
docker image build -t jenkins-local .
```

## Run jenkins server

```sh
docker container run -d \
                     -p 8080:8080 \
                     -p 50000:50000 \
                     -v jenkins_home:/var/jenkins_home \
                     --name jenkins-server \
                     --restart=on-failure \
                     jenkins-local
```

## Find initial admin password

```sh
docker exec -it jenkins-server cat /var/jenkins_home/secrets/initialAdminPassword
```