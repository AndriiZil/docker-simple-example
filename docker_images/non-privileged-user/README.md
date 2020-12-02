### Створимо імедж на базі докерфайла
```
    docker image build -t centos7/nonroot:v1 .
```
### Створимо контейнер і зайдемо у нього інтерактивно, ми увійшли під юзером
```
    docker container run -it --name test-build centos7/nonroot:v1 /bin/bash
```
### Запустимо зупинений контейнер
```
    docker container start test-build
```
### Зайдемо інтерактивно в контейнер під root юзером
```
    docker container exec -u 0 -it test-build /bin/bash
```
### Перевіримо під яким ми юзером
```
    whoami
```