## Create tomcat image

```sh
docker image build -t tomcat-local .
```

## Run tomcat server

```sh
docker container run -it \
                     --rm \
                     --name tomcat-server \
                     -p 8888:8080 \
                     tomcat-local
```