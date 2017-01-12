# О репозитории

###Dockerfile для запуска PostgreSQL с установленным расширением jsquery.

Для запуска на Windows 7 необходима версия VirtualBox > 5.1.10

Образ на docker hub - https://hub.docker.com/r/nikozavr/postgresqlpro/

Последовательность команд для запуска:

* Сборка образа из исходных кодов

  `docker build -t $IMAGENAME .`

* Запуск контейнера с использование собранного образа
 
  `docker run -it -d -p 5432:5432 --name=$CONTAINERNAME -e POSTGRES_PASSWORD=$PASSWORD -v $HOSTDIR:/var/lib/postgresql/data/ $IMAGENAME`

    , где
    * `$IMAGENAME` - имя образа
    * `$CONTAINERNAME`- имя контейнера
    * `$PASSWORD` - пароль для доступа к базе
    * `$HOSTDIR` - адрес директории на устройстве, которая будет содержать данные и монтироваться к контейнеру
