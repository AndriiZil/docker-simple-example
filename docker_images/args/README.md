```
    docker image build -t linuxacademy/weather-app:v3 --build-arg SRC_DIR=/var/code .
```

```
    docker container run -d --name weather-app3 -p 8085:3000 linuxacademy/weather-app:v3
```