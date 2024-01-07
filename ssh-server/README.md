## 개선사항

* root 비밀번호 변경부분 감추기 - [Build secrets in Docker and Compose v1, the secure way](https://pythonspeed.com/articles/build-secrets-docker-compose/) 참고하기

## Build ssh-server image

```sh
docker image build -t ssh-server .
```

## Run ssh-server container

```sh
docker container run --privileged -d -p 10022:22 -p 8888:8888 -v /sys/fs/cgroup:/sys/fs/cgroup --name ssh-server ssh-server
```

## SSH Server root 비밀번호

```
Docker!
```

## SSH 실행

```sh
service ssh start
```

## IP 및 SSH 포트 확인

```sh
# IP 확인
ifconfig

# SSH 포트 확인
netstat -ntlp | grep sshd
```

## Reference

* [docker "Couldn't find an alternative telinit implementation to spawn"](https://stackoverflow.com/questions/36545105/docker-couldnt-find-an-alternative-telinit-implementation-to-spawn)
* [How to install Docker inside my ubuntu container?](https://stackoverflow.com/questions/59174838/how-to-install-docker-inside-my-ubuntu-container)
* [도커 컨테이너 안에서 도커 실행하기(Docker in Docker, Docker Out of Docker)](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=isc0304&logNo=222274955992)