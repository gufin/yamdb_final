FROM python:3.7-slim

# Создать директорию вашего приложения.
RUN mkdir /app

# Скопировать с локального компьютера файл зависимостей
# в директорию /app.
COPY requirements.txt /app
COPY manage.py /app

# Выполнить установку зависимостей внутри контейнера.
RUN pip3 install -r /app/requirements.txt --no-cache-dir

# Скопировать содержимое директории /api_yamdb c локального компьютера
# в директорию /app.
COPY api/ /app/api
COPY api_yamdb/ /app/api_yamdb
COPY media/ /app/media
COPY reviews/ /app/reviews
COPY sent_emails/ /app/sent_emails
COPY static/ /app/static
COPY templates/ /app/templates
COPY users/ /app/users

# Сделать директорию /app рабочей директорией.
WORKDIR /app

# Выполнить запуск сервера разработки при старте контейнера.
CMD ["gunicorn", "api_yamdb.wsgi:application", "--bind", "0:8000" ]