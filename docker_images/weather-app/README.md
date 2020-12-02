### Зборка образа к конкретного докерфайла
```
    docker image build -t linuxacademy/weather-app:path-example1 -f Dockerfile.test .
```
### Зборка образа з передачею параметрів всередину
```
    docker image build -t linuxacademy/weather-app:path-example2 --label com.linuxacademy.version=v1.8 -f Dockerfile.test .
```
### Зборка образа за допомогою стандартного вводу виводу
```
    docker image build -t linuxacademy/nginx:stind --rm -<<EOF
    FROM nginx:latest
    VOLUME ["/usr/share/nginx/html/"]
    EOF
```
### Зборка по віддаленому Git репозиторію і його хешу де лежить сам докерфайл
```
    docker image build -t linuxacademy/weather-app:github https://github.com/linuxacademy/content-weather-app.git#remote-build
```
### Установка з тар файла
```
    docker image build -t linuxacademy/weather-app:from-tar - < weather-app.tar.gz
```