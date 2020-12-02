### Створюємо образ
```
    docker image build -t linuxacademy/weather-app:multi-stage-build --rm --build-arg VERSION=1.5 .
```
### Створюємо контейнер на базі образа
```
    docker container run -d --name multi-stage-build -p 8087:3000 linuxacademy/weather-app:multi-stage-build
```