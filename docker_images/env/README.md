```
    docker image build -t linuxacademy/weather-app:v2 .
```

```
    docker container run -d --name weather-dev -p 8082:3001 --env PORT3001 linuxacademy/weather-app:v2
```

```
    docker container run -d --name weather-app2 -p 8083:3001 --env PORT=3001 --env NODE_ENV=production linuxacademy/weather-app:v2
```

```
    docker container run -d --name weather-prod -p 8084:3000 --env NODE_ENV=production linuxacademy/weather-app:v2
```