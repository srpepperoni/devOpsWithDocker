# Exercise 3.4

## Backend Dockerfile

```yaml
FROM node:alpine

WORKDIR /mydir
RUN apk add --no-cache git && \
git clone https://github.com/docker-hy/backend-example-docker && \
apk del git && \
cd backend-example-docker && npm install

EXPOSE 8000

CMD ["npm","start","--prefix","backend-example-docker/"]
```

## Frontend Dockerfile

```yaml
FROM node:alpine

WORKDIR /mydir
RUN apk add --no-cache git && \
git clone https://github.com/docker-hy/frontend-example-docker && \
cd frontend-example-docker && npm install && \
apk del git

EXPOSE 5000

CMD ["npm","start","--prefix","frontend-example-docker/"]
```
