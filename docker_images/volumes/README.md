### Створюємо image на базі Dockerfile
```
    docker image build -t linuxacademy/nginx:v1 .
```
### Створюємо контейнер на базі образа
```
    docker container run -d --name nginx-volume linuxacademy/nginx:v1
```