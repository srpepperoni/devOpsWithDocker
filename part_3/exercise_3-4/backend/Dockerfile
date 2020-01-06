FROM node:alpine

WORKDIR /mydir
RUN apk add --no-cache git && \
git clone https://github.com/docker-hy/backend-example-docker && \
apk del git && \
cd backend-example-docker && npm install

EXPOSE 8000

CMD ["npm","start","--prefix","backend-example-docker/"]