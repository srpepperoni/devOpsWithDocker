# Exercise 1.13

## Dockerfile

```
FROM openjdk:8-jdk

WORKDIR /mydir

RUN git clone https://github.com/docker-hy/spring-example-project.git
RUN cd spring-example-project && ./mvnw package

EXPOSE 8080

CMD cd spring-example-project && java -jar ./target/docker-example-1.1.3.jar
```

## Command

```
$>docker build -t backjdk .
$>docker run -d -p 8080:8080 backjdk

```
