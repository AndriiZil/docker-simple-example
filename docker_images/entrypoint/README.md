### 
```
    git clone https://github.com/linuxacademy/content-weather-app.git src
```
### 
```
    docker image build -t linuxacademy/weather-app:v4 .
```
### 
```
    docker container run -d --name weather-app5 -p 8083:3001 linuxacademy/weather-app:v4 echo "Hello World"
```