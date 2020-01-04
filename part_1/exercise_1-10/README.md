# Exercise 1.10

## Dockerfile

```
FROM ubuntu:16.04

WORKDIR /mydir
RUN apt-get update && apt-get install -y git && apt-get install -y curl && apt-get install -y nodejs
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt install -y nodejs
RUN git clone https://github.com/docker-hy/frontend-example-docker
RUN cd frontend-example-docker && npm install && npm run build

EXPOSE 5000

CMD ["npm","start","--prefix","frontend-example-docker/"]

```

## Commands

This commands were wrote from Dockerfile directory.

```
$>docker build -t exercise10 .
$>docker run -d -p 5000:5000 exercise10

```

