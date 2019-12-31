# Exercise 2.6

## Backend Dockerfile

```
FROM ubuntu:16.04

WORKDIR /mydir
RUN apt-get update && apt-get install -y git && apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt install -y nodejs
RUN git clone https://github.com/docker-hy/backend-example-docker
RUN cd backend-example-docker && npm install

EXPOSE 8000

ENV FRONT_URL=http://localhost:5000
CMD ["npm","start","--prefix","backend-example-docker/"]
```

## Frontend Dockerfile

```
FROM ubuntu:16.04

WORKDIR /mydir
RUN apt-get update && apt-get install -y git && apt-get install -y curl && apt-get install -y nodejs
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt install -y nodejs
RUN git clone https://github.com/docker-hy/frontend-example-docker
RUN cd frontend-example-docker && npm install && npm run build

EXPOSE 5000

ENV API_URL=http://localhost:8000
CMD ["npm","start","--prefix","frontend-example-docker/"]
```

## Docker-compose Yaml

```yaml
version: '3.5'
services:
  backend:
      build: ./backend
      ports:
        - 8000:8000
      environment:
        - REDIS=cache
        - DB_HOST=database
        - DB_NAME=mydatabase
        - DB_USERNAME=dbname
        - DB_PASSWROD=password
      depends_on:
        - database
  frontend:
      build: ./frontend
      ports:
        - 5000:5000
  cache:
      image: redis:5.0.7
      ports:
        - 6379:6379
  database:
      image: postgres
      restart: unless-stopped
      environment:
        - POSTGRES_PASSWORD=password
        
```
