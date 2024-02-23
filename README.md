This is a Docker setup for a web application based on Django.

The Django application is served by Gunicorn (WSGI application).
We use NginX as reverse proxy and static files server. Static and media files are persistently stored in volumes.
Multiple Postgres databases can be used. Data are persistently stored in volumes.
Python dependencies are managed through pipenv, with Pipfile and Pipfile.lock.
Support for multiple environment settings (variable DJANGO_SETTINGS_MODULE is passed to the djangoapp service).
You need to install Docker and Docker-Compose.
Build
docker-compose build or make build.

Migrate databases
docker-compose run --rm djangoapp hello/manage.py migrate or make migrate.

Collect static files
docker-compose run --rm djangoapp hello/manage.py collectstatic --no-input' or make collectstatic.

Run
docker-compose up or make run.
Django==2.2.27
psycopg2==2.8.3
What is Redis?
Redis is an in-memory data structure store that can be used as a caching engine. Since it keeps data in RAM, Redis can deliver it very quickly. Redis is not the only product that we can use for caching. Memcached is another popular in-memory caching system, but many people agree that Redis is superior to Memcached in most circumstances. Personally, we like how easy it is to set up and use Redis for other purposes such as Redis Queue.

gunicorn==19.9.0
