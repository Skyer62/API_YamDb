# API_YamDb
Проект YaMDb собирает отзывы пользователей на произведения. Произведения делятся на категории: «Книги», «Фильмы», «Музыка». Произведению может быть присвоен жанр из списка предустановленных (например, «Сказка», «Рок» или «Артхаус»). Новые жанры может создавать только администратор. Благодарные или возмущённые читатели оставляют к произведениям текстовые отзывы и выставляют произведению рейтинг (оценку в диапазоне от одного до десяти). Из множества оценок автоматически высчитывается средняя оценка произведения.
# Стек технологий
- Python + Django REST Framework
- Simple JWT - работа с токеном
- Django-filter - фильтрация запросов
- PostgreSQL - база данных
- Git - система контроля версий
# Установка
1. Клонирйте репозиторий с проектом
```sh
https://github.com/vadim62/yamdb_final
```
2. Добавьте в корневую папку проекта файл .env содержащий данные о базе данных:
```sh

DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres(example)
POSTGRES_USER=postgres(example)
POSTGRES_PASSWORD=postgres(example)
DB_HOST=db(example)
DB_PORT=5432(example)
SECRET_KEY=123123123132(example)

```
3. Установите Docker(docker.com) и в корневой директории проекта выполните сборку и запуск контейнера:
```sh
docker-compose up --build
```
4. Выполните миграции:
```sh
docker-compose exec web python3 manage.py makemigrations api

docker-compose exec web python3 manage.py migrate api
```

5. Создайте superuser и соберите статику:
```sh
docker-compose exec web python manage.py createsuperuser

docker-compose exec web python manage.py collectstatic --no-input 
```
Полная документация (redoc.yaml) доступна по адресу http://127.0.0.1/redoc/
