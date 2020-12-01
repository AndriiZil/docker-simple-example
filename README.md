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
### Файл docker-compose.yaml
```
    version: '3.5'
    
    services:
      nginx:
        build: ./docker/nginx
        ports:
          - '8080:80'
        volumes:
          - ./:/app
          - ./docker/nginx/nginx.conf:/etc/nginx/nginx.conf
          - ./docker/nginx/conf.d:/etc/nginx/conf.d
        depends_on:
          - php
    
      php:
        build: ./docker/php
        volumes:
          - ./:/app
```
### Подивитися детальнішу інформацію про образ
```
    docker image inspect
```
### Запуск контейнера -P привяже рандомний порт на хості
```
    docker container run -P -d nginx
```
### Інформація про контейнер 
```
    docker container inspect e7a599535bc4
```
### Підключення до стандартного вводу виводу контейнера
```
    docker container attach e7a599535bc4
```
### Провалимось в середину контейнера і можемо писати команди
```
    docker container exec -it e7a599535bc4 /bin/bash
```
### Виводимо вміст папки без входа в контейнер
```
    docker container exec -it e7a599535bc4 ls /usr/share/nginx/html/
```
### Зупиняє та удаляє контейнер
```
    docker container rm -f e7a599535bc4
```
### Видалить всі не запущені контейнери
```
    docker container prune -f
```
### Видаляємо my_busybox контейнер
```
    docker container run --rm busybox
```
### Назначаємо імя контенеру my_busybox
```
    docker container run --name my_busybox busybox
```
### Відкрити порт 3000 без перенаправлення
```
    docker container run -d --expose 3000 nginx
```
### Перенаправляє на 80 порт і відкриває 3000
```
    docker container run -d --expose 3000 -p 80:3000 nginx
```
### Відкриває 3000 порт і перенаправляє з порта контейнера 80 на 8008 хост
```
    docker container run -d --expose 3000 -p 8080:80 nginx
```
### Перенаправляє різні порти 
```
    docker container run -d -p 8081:80/tcp -p 8081:80/udp nginx
```
### Показує список портів
```
    docker container port 01b98b8e9245
```
### Перенапрявляє порт по дефолту
```
    docker container run -d -P nginx
```
### Заходимо інтерактивно в консоль
```
    docker container run -it nginx /bin/bash
```
### Запускаємо nginx при виході контенер зупиняється
```
    nginx -g 'daemon off;'
```
### Показати вміст папки контейнера
```
    docker container exec -it 3638ac20ae82 ls /usr/share/nginx/html
```
### Переходимо в інтерактивний режим контейнера
```
    docker container exec -it 3638ac20ae82 /bin/bash
```
### Скачати аплікацію з погодою і відкрити порт localhost:80
```
    docker container run --name weather-app -d -p 80:3000 linuxacademycontent/weather-app
```
### Дивитися логи по контейнер id
```
    docker logs 61ddc2d8555c
```
### Список допомоги по мережах
```
    docker network -h
```
### Список мереж
```
    docker network ls
```
### Детальний лог по bridge
```
    docker network inspect bridge
```
### По замовчуванню створить мережу типу bridge
```
    docker network create br00
```
### видаляємо мережу по назві або id
```
    docker network rm br00 
```
### Видалить всі мережі які не використовуються крім default
```
    docker network prune 
```
### Створимо новий контейнер і назвемо його
```
    docker container run -d --name network-test03 -p 8081:80 nginx
```
### Створимо мережу
```
    docker network create br01
```
### Підключимо мережу до контейнера
```
    docker network connect br01 network-test03
```
### подивимось підєднаний контейнер 
```
    docker container inspect d4cabaf8f86d
```
### видалемо мережу з контейнера
```
    docker network disconnect br01 network-test03
```
### Створюємо підмережу
```
    docker network create --subnet 10.1.0.0/24 --gateway 10.1.0.1 br02
```
### Створюємо контейнер з діапазоном Ip адресів
```
    docker network create --subnet 10.1.0.0/16 --gateway 10.1.0.1 \
    --ip-range=10.1.4.0/24 --driver=bridge --label=host4network br04
```
### Прикріпляємо мережу до контенера і скачуємо сам centos образ якщо такого немає
```
    docker container run --name network-test01 -it --network br04 centos /bin/bash
```
### Присвоюємо Ip адресу контейнеру 10.1.4.102
```
    docker container run -d --name network-test02 --ip 10.1.4.102 --network br04 nginx
```
### Створимо внутрішню мережу bridge і назвемо її localhost
```
    docker network create -d bridge --internal localhost
```
### Створимо контейнер mysql і запустимо його в фоні
```
    docker container run -d --name test_mysql \
    -e MYSQL_ROOT_PASSWORD=P4sSw0rd0 \
    --network localhost mysql:5.7
```
### Створюємо контейнер який буде пінгувати mysql
```
    docker container run -it --name ping-mysql \
    --network bridge \
    centos
```
### Показати список команд з томами
```
    docker volume -h
```
### Показати всі томи
```
    docker volume ls
```
### Створити volume
```
    docker volume create test-volume1
```
### Подивитися всі доступні команди
```
    docker volume create -h
```
### Подивитися конфігурацію конкретного волюма
```
    docker volume inspect test-volume1
```
### Видалити конкретний volume по його назві
```
    docker volume rm test-volume1
```
### Видалити всі томи що не використовуються
```
    docker volume prune
```
### Прибайндюємо папку таргет з локального компютера в папку app нашого контейнера
```
    docker container run -d --name nginx-bind-mount1 --mount type=bind,source="$(pwd)"/target,target=/app nginx
```
### Дивимось у розділ Mount у файлі
```
    docker container inspect nginx-bind-mount1
```
### Зходимо інтерактивно в докер і дивимось файли які можемо створити локально в target і побачити їх в контейнері папки app
```
    docker container exec -it nginx-bind-mount1 /bin/bash
```
### створюємо волюм не створюючи папки target2
```
    docker container run -d --name nginx-bind-mount2 -v "$(pwd)"/target2:/app nginx
```
### створимо файл і папку локально
```
    docker container exec -it nginx-bind-mount2 touch /app/file3.txt
```
### Якщо зайти в контейнер то ми побачимо всередині папки app файл file3.txt
```
    docker container exec -it nginx-bind-mount2 /bin/bash
```
### Створимо папку nginx з конфігом і прикріпимо волюм всередину де джерело "$(pwd)"/nginx/nginx.conf а призначений шлях всередині контенера /etc/nginx/nginx.conf
```
    docker container run -d --name nginx-bind-mount3 -v "$(pwd)"/nginx/nginx.conf:/etc/nginx/nginx.conf nginx
```
### Створимо волюм
```
    docker volume create html-volume
```
### Привяжемо том до каталога
```
    docker container run -d --name nginx-volume1 --mount type=volume,source=html-volume,target=/user/share/nginx/html nginx
```
### Змінюємо вміст файла index.html
```
    sudo vi /var/lib/docker/volumes/html-volume/_data/index.html
```
### Створимо волюм без можливості редагування файлів
```
    docker run -d --name nginx-volume3 --mount source=html-volume,target=/usr/share/nginx/html,readonly nginx
```
### Білдимо образ із докерфайла -t linuxacademy/weather-app назва образа і v1 тег
```
    docker image build -t linuxacademy/weather-app:v1 .
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
### 
```
    
```


