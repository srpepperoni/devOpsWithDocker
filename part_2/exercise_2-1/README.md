# Exercise 2.1

## Dockerfile

```
FROM devopsdockeruh/first_volume_exercise
```

## Docker-Compose Yaml

```yaml
version: '3.5' 

services: 
    first_volume_exercise: 
      image: devopsdockeruh/first_volume_exercise 
      build: . 
      volumes: 
        - ./logs.txt:/usr/app/logs.txt
      container_name: first_volume
```

## Logs

```
Sun, 08 Dec 2019 22:52:50 GMT
Sun, 08 Dec 2019 22:52:53 GMT
Sun, 08 Dec 2019 22:52:56 GMT
Sun, 08 Dec 2019 22:52:59 GMT
Secret message is:
"Volume bind mount is easy"

```

