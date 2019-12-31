# Exercise 2.7

```yaml
version: '3.5'
services:
  training:
      build: ./training
      restart: always
      volumes:
        - ./src/model:/src/model
        - ./src/imgs:/src/imgs
  backend:
      build: ./backend
      ports:
        - 5000:5000
      volumes:
        - ./src/model:/src/model
      depends_on:
        - training
  frontend:
      build: ./frontend
      ports:
        - 3000:3000
        
volumes:
  model:
  imgs:
```
