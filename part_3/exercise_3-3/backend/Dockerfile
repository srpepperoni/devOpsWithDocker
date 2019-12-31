FROM ubuntu:16.04

WORKDIR /mydir
RUN apt-get update && apt-get install -y git && apt-get install -y curl && \
curl -sL https://deb.nodesource.com/setup_10.x | bash && \
apt install -y nodejs && \
git clone https://github.com/docker-hy/backend-example-docker && \
apt-get purge -y --auto-remove curl && \
apt-get purge -y --auto-remove git && \
rm -rf /var/lib/apt/lists/* && \
cd backend-example-docker && npm install && \
useradd -m app && \
chown -R app:app /mydir

USER app

EXPOSE 8000

ENV FRONT_URL=http://localhost:5000
CMD ["npm","start","--prefix","backend-example-docker/"]