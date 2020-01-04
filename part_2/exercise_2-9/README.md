# Exercise 2.9

```yaml
version: '3.5'  

services:
    redis:
        image: redis
        ports:
            - 6379:6379
    frontend:
        ports:
            - 5000:5000
        build: ./frontend
    backend:
        ports:
            - 8000:8000
        build: ./backend
        environment:
            - REDIS=redis
            - DB_USERNAME=postgres
            - DB_PASSWORD=root
            - DB_NAME=postgres
            - DB_HOST=postgreserver
        depends_on:
            - postgreserver
    postgreserver:
        image: postgres
        restart: always
        environment:
            POSTGRES_PASSWORD: root
            PGDATA: /database/postgres/data
        volumes:
            - postgres:/database/postgres/data
    nginx:
        image: nginx
        restart: always
        ports:
            - 80:80
        environment:
            - NGINX_HOST=localhost
            - NGINX_PORT=80
        volumes:
            - ./nginx/nginx.conf:/etc/nginx/nginx.conf:ro
        depends_on:
            - frontend
            - backend
volumes:
  postgres:
```
