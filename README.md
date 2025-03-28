# PgAdmin4 Setup

Данная инструкция описывает процесс развертывания `PgAdmin4` с использованием `Docker-compose`.

## Требования
- `Docker` и `Docker-compose` установлен на вашей системе.

## Шаги

1. Создайте файл `docker-compose.yml` со следующим содержимым:

```yaml
services:
  pg_admin:
    image: dpage/pgadmin4
    environment:
      - PGADMIN_DEFAULT_EMAIL=user@domain.com
      - PGADMIN_DEFAULT_PASSWORD=SuperSecret
    ports:
      - 85:80
```

2. Замените значения переменных окружения `PGADMIN_DEFAULT_EMAIL` и `PGADMIN_DEFAULT_PASSWORD` на ваши предпочтительные значения.

3. Сохраните файл `docker-compose.yml`.

4. Откройте терминал и перейдите в директорию, где находится файл `docker-compose.yml`.

5. Запустите контейнер с помощью команды:

```
docker-compose up -d
```

6. Дождитесь, пока контейнер будет развернут.

7. Откройте веб-браузер и перейдите по адресу `http://localhost:85`.

8. Введите электронную почту и пароль, которые вы указали в файле `docker-compose.yml`, и нажмите "Login".

Теперь вы можете использовать `PgAdmin4` для управления своими базами данных `PostgreSQL`.

## Дополнительные ресурсы
- [Официальная документация PgAdmin4](https://www.pgadmin.org/docs/)
- [Документация по работе с контейнером](https://www.pgadmin.org/docs/pgadmin4/latest/container_deployment.html)
- [Документация Docker Compose](https://docs.docker.com/compose/)
- [Образ PgAdmin4 на DockerHub](https://hub.docker.com/r/dpage/pgadmin4/)
