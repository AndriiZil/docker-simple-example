### Docker for developers


### Скачати імедж з DockerHub
```
    docker run -it nginx bash
```

### Скачати і запустити контейнер
```
    docker run
```

### Увійти інтерактивно в контейнер
```
    -it
```

### Імя контейнера для скачування в DockerHub
```
    nginx
```

### Команду яку потрібно виконати всередині контейнера
```
    bash
```

### Показати всі імеджі скачані з DockerHub в локальному реєстрі
```
    docker images
```

### Виконати команду cat над файлом nginx.conf
```
    docker run nginx cat /etc/nginx/nginx.conf
```

### Стартувати новий контейнер на базі образа nginx
```
    docker run nginx
```

### Прокинути порт на зовні 8080 для доступу через localhost
```
    docker run -p 8080:80 nginx
```

### Порт всередині контейнера
```
    80
```

### Запуск в фоновому режимі
```
    docker run -p 8080:80 -d nginx
```

### Запущені контейнери
```
    docker ps
```
### Подивитися всі контейнери
```
    docker ps -a
```

### Поставити контейнер на паузу 
```
    docker pause 68bd53695a6d (<CONTAINER ID>)
```

### Відновити роботу після паузи
```
    docker unpause 68bd53695a6d
```
### Зупинити контейнер
```
    docker stop 68bd53695a6d
```
### Стартувати контейнер
```
    docker start 68bd53695a6d
```
### Вбити контейнер
```
    docker kill 68bd53695a6d
```
### Подивитися логи контейнера
```
    docker logs 68bd53695a6d
```
### Дивитися логи в реальному режимі
```
    docker logs -f 68bd53695a6d
```
### Статистика по контейнерах
```
    docker stats
```
### Скачує образ але не створює і не запускає контейнер
```
    docker pull nginx
```
### прокинути файли в контейнер в папку app
```
    docker run -p 8080:80 -v ~/Documents/Docker-examples/PHP:/app nginx
```
### Зайти всередину контейнера
```
    docker exec -it c70fa51767e2 bash 
```
### Види взаємодії з контейнером
- port
- files
- envs

### Створення образів за допомогою Dockerfile
```
    FROM php:7.3-cli
    MAINTAINER AZilnyk <andrii.zilnyk@gmail.com>

    RUN apt update && apt install -y mc

    COPY . /app
    WORKDIR /app
```
### Зібрати контейнер
```
    docker build .
``` 
### Прописуємо конфігурації в docker-compose.yaml
```
    docker-compose up --build -d
```
### 
```
```
### 
```

```
### 
```

```
### 
```

```
### 
```

```