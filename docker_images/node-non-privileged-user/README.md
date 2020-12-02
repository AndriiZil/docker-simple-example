### Клонуємо репозиторій з погодою
```
    git clone https://github.com/linuxacademy/content-weather-app.git src
```

### Створюємо імедж на базі Dockerfile
```
    docker image build -t linuxacademy/weather-app-nonroot:v1 .
```
### Стартуємо контейнер на базі образа
```
    docker container run -d --name weather-app-nonroot -p 8086:3000 linuxacademy/weather-app-nonroot:v1
```