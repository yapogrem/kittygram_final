# Как запустить проект:

На удаленном сервере создать папку проекта kittygram.
В данной папке создать файл .env, и наполнить его данными. (Для примера подготовлен файл .env.example).

Скопировать в папку kittygram файл docker-compose.production.yml.

Выполнить команды:
```
sudo docker compose -f docker-compose.production.yml pull
sudo docker compose -f docker-compose.production.yml down
sudo docker compose -f docker-compose.production.yml up -d
sudo docker compose -f docker-compose.production.yml exec backend python manage.py migrate
sudo docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
sudo docker compose -f docker-compose.production.yml exec backend cp -r /app/static/. /backend_static/static
```

Проверить работу севиса https://ya0961.ddns.net/.

### Как внести изменения в проект:

Для внесения изменений в проект достаточно внести и сохранить изменения в ветке main.