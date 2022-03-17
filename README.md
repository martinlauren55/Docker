# Docker
Instructions for working with Docker

# Команды для консоли

</br>

## IMAGES
Посмотреть все созданные images:</br>
**docker images**</br>

### Удаление
Удалить image по IMAGE_ID:</br>
**docker rmi {IMAGE_ID}**</br>

Удалить все локальные images:</br>
**docker image rm $(docker images -a -q)**</br>

**docker image rmi $(docker images -a -q)**</br>

Удалить все:</br>
**docker system prune**</br>

</br>

## CONTAINERS

Посмотреть запущенные контейнеры:</br>
**docker ps / docker container ls**</br>

Посмотреть запущенные контейнеры с дополнительной иформацией:</br>
**docker container ls -a -s**

Запуск докера на основе images (клонирование и запуск):</br>
**docker run {IMAGE_ID}**</br>

Выполнение неограниченное количество команда внутри контейнера</br>
**docker run -it ubuntu:18.10 /bin/bash**</br>
Мы можем подключиться к консоли виртуальной ОС (Ubuntu 18.10), и выполнять любое количество команд без завершения работы контейнера, для этого, запустим команду:</br>
Опция -it вместе с /bin/bash даёт доступ к выполнению команд в терминале внутри контейнера Ubuntu.</br>
Теперь, внутри этого контейнера можно выполнять любые команды, применимые к Ubuntu. Вы же можете представлять это как мини виртуальную машину, условно, к консоли которой мы подключились по SSH.</br>


Запуск докера и удаление его после остановки:</br>
**docker run --rm {IMAGE_ID}**</br>

Посмотреть запущенные и остановленные контейнеры:</br>
**docker ps -a**</br>

**SOFT** Остановить контейнер по его имени CONTAINER_NAMES:</br>
**docker container stop {CONTAINER_NAMES}**</br>

**HARD** Остановить контейнер по его имени CONTAINER_NAMES:</br>
**docker container kill {CONTAINER_NAMES}**</br>

Сборка образа:</br>
**docker image build -t {name} .**</br>
*-t {name}* - my_name_container</br>
*.* - место от куда собирать docker image (место где лежит dockerfile)</br>

</br>

### Удаление

Удалить контейнер по его имени  CONTAINER_NAMES:</br>
**docker rm {CONTAINER_NAMES}**</br>

Удалить все контейнеры, которые не выполняются:</br>
**docker container rm $(docker ps -a -q)**</br>

</br>

## Разные команды

Вот команда, которая выводит сведения о версиях клиента и сервера Docker:</br>
**docker version**</br>

Удалить неиспользуемые контейнеры, сети и образы, которым не назначено имя и тег:</br>
**docker system prune**</br>


## Docker Compose

Запуск Docker Compose файла</br>
**docker-compose -f {docker-compose_file.yml} up**</br>

</br>

## Bash

Открыть контейнер через Bash </br>
**docker exec -it {CONTAINER_ID} /bin/bash**</br>
Команда exec позволяет выполнить команду внутри запущенного контейнера. В нашем случае, мы выполнили **/bin/bash**, что позволило нам подключиться к терминалу внутри контейнера </br>
Для выхода, как обычно, выполним exit</br>
