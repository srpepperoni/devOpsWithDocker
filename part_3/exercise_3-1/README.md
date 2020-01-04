# Exercise 3.1

## Backend Dockerfile

```
FROM ubuntu:16.04

WORKDIR /mydir
RUN apt-get update && apt-get install -y git && apt-get install -y curl && \
curl -sL https://deb.nodesource.com/setup_10.x | bash && \
apt install -y nodejs && \
git clone https://github.com/docker-hy/backend-example-docker && \
apt-get purge -y --auto-remove curl && \
apt-get purge -y --auto-remove git && \
rm -rf /var/lib/apt/lists/* && \
cd backend-example-docker && npm install

EXPOSE 8000

ENV FRONT_URL=http://localhost:5000
CMD ["npm","start","--prefix","backend-example-docker/"]
```

## Frontend Dockerfile

```
FROM ubuntu:16.04

WORKDIR /mydir
RUN apt-get update && apt-get install -y git && apt-get install -y curl && apt-get install -y nodejs && \
curl -sL https://deb.nodesource.com/setup_10.x | bash && \
apt install -y nodejs && \
git clone https://github.com/docker-hy/frontend-example-docker && \
apt-get purge -y --auto-remove curl && \
apt-get purge -y --auto-remove git && \
rm -rf /var/lib/apt/lists/* && \
cd frontend-example-docker && npm install && npm run build

EXPOSE 5000

ENV API_URL=http://localhost:8000
CMD ["npm","start","--prefix","frontend-example-docker/"]
```
