## Build Docker Image

```sh
docker image build -t dind .
```

## Create Docker Container

```sh
docker container run --privileged -d --name dind dind
docker container run --privileged --name docker-server -itd -p 10022:22 -p 8081:8080 -e container=docker -v /sys/fs/cgroup:/sys/fs/cgroup edowon0623/docker:latest /usr/bin/init
```
