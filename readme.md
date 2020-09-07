# Web приложение в Docker на Django или Flask 

- Nginx
- Django + Gunicorn
- Postgresql



### Настройки

в папке config/env_file
нужно положить файлы:
 
.env
с содержимым:

```dotenv
# cat .env
DEBUG=1
SECRET_KEY=foo
DJANGO_ALLOWED_HOSTS=localhost,127.0.0.1,[::1]
SQL_ENGINE=django.db.backends.postgresql
SQL_HOST=database
SQL_PORT=5432

SQL_USER=user
SQL_PASSWORD=pass
SQL_DATABASE=table
```

.env.database
с содержимым:
```dotenv
# cat .env.database
POSTGRES_USER=user
POSTGRES_PASSWORD=pass
POSTGRES_DB=table
```

#### pipenv
Для работы с pipenv необходимо запускать среду в системе (без активации virtualenv):

``` shell script
pipenv install --system --deploy --ignore-pipfile
```


## Django 
#### Миграции

Применить миграции
```shell script
docker-compose exec web python manage.py migrate --noinput

```


