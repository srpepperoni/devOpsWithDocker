# Exercise 1.11

## Dockerfile

```
FROM ubuntu:16.04

WORKDIR /mydir
RUN apt-get update && apt-get install -y git && apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt install -y nodejs
RUN git clone https://github.com/docker-hy/backend-example-docker
RUN cd backend-example-docker && npm install

EXPOSE 8000

CMD ["npm","start","--prefix","backend-example-docker/"]
```

## Terminal

```
Script started on 2019-12-08 01:59:04+0000
[root@ip-172-31-20-228 exercise_1-11]# docker run -d -p 8000:8000 -v $(pwd)/backend-example-docker/logs.txt:/mydir/backend-example-docker/logs.txt exercise_1-11
dad139a3c3909d0b379ef2d913ccbe4bbe23793f4a1b7f82aa34cba49b4fa85d
[root@ip-172-31-20-228 exercise_1-11]# cd ..
[root@ip-172-31-20-228 part_1]# cd exercise_1-11/backend-example-docker/
[root@ip-172-31-20-228 backend-example-docker]# cat logs.txt 
12/8/2019, 1:55:36 AM: Connection received in root
12/8/2019, 1:55:55 AM: Connection received in root
12/8/2019, 1:57:57 AM: Connection received in root
[root@ip-172-31-20-228 backend-example-docker]# curl localhost:8000
Port configured correctly, generated message in logs.txt
[root@ip-172-31-20-228 backend-example-docker]# cat logs.txt 
12/8/2019, 1:55:36 AM: Connection received in root
12/8/2019, 1:55:55 AM: Connection received in root
12/8/2019, 1:57:57 AM: Connection received in root
12/8/2019, 2:01:06 AM: Connection received in root
[root@ip-172-31-20-228 backend-example-docker]# exit
exit

Script done on 2019-12-08 02:01:14+0000

```

