# 🛠 api_yamdb
The api implements the ability to create reviews, comment on these reviews, the ability to add new categories of content and divide content into genres. API user authentication implemented through jwt tokens

- Python 3.8
- Django 2.2
- Django Rest Framework 3.12
- Docker
- PostgreSQL

# 🚀 Project installation

- Clone repository and going:
```sh
    git clone ...
    cd /infra
```

- Change nginx settings (servername)
- Create .env file (like template)
 
```sh
SECRET_KEY=... 
DEBUG=... 
ALLOWED_HOSTS=... 
DB_ENGINE=... 
DB_NAME=... 
POSTGRES_USER=... 
POSTGRES_PASSWORD=... 
DB_HOST=... 
DB_PORT=...
```

- 🐳 Deploy and launch app:
```sh
docker-compose up -d --build
```
- Make migrations:
```sh
docker-compose exec web python manage.py migrate
```

- Fill database by data (optionally)
```sh
docker-compose exec web python manage.py loaddata fixtures.json
```
- Create superuser
```sh
docker-compose exec web python manage.py createsuperuser
```
- Collect static
```sh
docker-compose exec web python manage.py collectstatic --no-input
```
# 😼 Author
Ivan Drobyshev

[redoc](http://84.201.175.228/redoc/)
