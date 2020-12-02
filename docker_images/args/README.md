### Білдимо імедж на базі Dockerfile і за допомогою --build-arg присвоюємо SRC_DIR
```
    docker image build -t linuxacademy/weather-app:v3 --build-arg SRC_DIR=/var/code .
```

### Створюємо контейнер з образа
```
    docker container run -d --name weather-app3 -p 8085:3000 linuxacademy/weather-app:v3
```