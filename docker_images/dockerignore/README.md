### Створюємо образ з Dockerfile
```
    docker image build -t linuxacademy/weather-app:v5 .
```
### Створюємо і запускаєм контейнер
```
    docker container run -d --name weather-app-ignore linuxacademy/weather-app:v5
```
### подивитися які файли та каталоги є включеними до контейнера
```
    docker container exec weather-app-ignore ls -la /var/node
```