# DRF, Postgres, PgAdmin Skeleton with Docker

Django project skeleton with Django Rest framework ready for Docker.

## Quickstart in Development

```
docker-compose up -d
docker-compose run restapi python manage.py migrate
docker-compose run restapi python manage.py createsuperuser
```

Access Django REST Framework at `localhost:8000`

Access Django Admin at `localhost:8000/admin`

To create new app:

```
docker-compose run restapi python manage.py startapp my-app project/apps/my-app
```

## Production

Depending on what you use:

```
docker build ./restapi your-app
docker tag your-app tag
docker push your-username/your-app:tag
```

# Postgres & PGAdmin Configuration

## Environments
This Compose file contains the following environment variables:

* `POSTGRES_USER` the default value is **django**
* `POSTGRES_PASSWORD` the default value is **django**
* `PGADMIN_PORT` the default value is **5050**
* `PGADMIN_DEFAULT_EMAIL` the default value is **lord@shuvro.me**
* `PGADMIN_DEFAULT_PASSWORD` the default value is **admin**

## Access to postgres: 
* `localhost:5432`
* **Username:** django (as a default)
* **Password:** django (as a default)

## Access to PgAdmin: 
* **URL:** `http://localhost:5050`
* **Username:** lord@shuvro.me (as a default)
* **Password:** admin (as a default)

## Add a new server in PgAdmin:
* **Host name/address** `database`
* **Port** `5432`
* **Username** as `POSTGRES_USER`, by default: `django`
* **Password** as `POSTGRES_PASSWORD`, by default `django`

For standalone Postgres & PGAdmin check the following repository
```
https://github.com/shuvro/docker-postgres-pgadmin
```
