FROM ubuntu:16.04

WORKDIR /mydir
RUN apt-get update && apt-get install -y git && apt-get install -y curl && apt-get install -y nodejs && \
curl -sL https://deb.nodesource.com/setup_10.x | bash && \
apt install -y nodejs && \
git clone https://github.com/docker-hy/frontend-example-docker && \
npm update caniuse-lite browserlist && \
apt-get purge -y --auto-remove curl && \
apt-get purge -y --auto-remove git && \
rm -rf /var/lib/apt/lists/* && \
cd frontend-example-docker && npm install && npm run build && \
useradd -m app && \
chown -R app:app /mydir

USER app

EXPOSE 5000

ENV API_URL=http://localhost:8000
CMD ["npm","start","--prefix","frontend-example-docker/"]

