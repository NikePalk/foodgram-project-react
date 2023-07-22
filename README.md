![Yamdb Workflow Status](https://github.com/NikePalk/foodgram-project-react/actions/workflows/main.yml/badge.svg?branch=master&event=push)

### Опиание проекта.
Cайт Foodgram, «Продуктовый помощник». Вы напишете онлайн-сервис и API для него. На этом сервисе пользователи смогут публиковать рецепты, подписываться на публикации других пользователей, добавлять понравившиеся рецепты в список «Избранное», а перед походом в магазин скачивать сводный список продуктов, необходимых для приготовления одного или нескольких выбранных блюд.

## Развёрнутый проект
- http://158.160.18.247/
- http://158.160.18.247/admin/

### Технологии:
- Django
- Python
- Docker

### Запуск проекта:
1. Клонируйте проект:
```
git clone https://github.com/NikePalk/foodgram-project-react.git
```
2. Подготовьте сервер:
```
scp docker-compose.yml <username>@<host>:/home/<username>/
scp nginx.conf <username>@<host>:/home/<username>/
scp .env <username>@<host>:/home/<username>/
```
3. Установите docker и docker-compose:
```
sudo apt install docker.io 
sudo apt install docker-compose
```
4. Соберите контейнер и выполните миграции:
```
sudo docker-compose up -d --build
sudo docker-compose exec backend python manage.py migrate
```
5. Создайте суперюзера и соберите статику:
```
sudo docker-compose exec backend python manage.py createsuperuser
sudo docker-compose exec backend python manage.py collectstatic --no-input
```
6. Скопируйте предустановленные данные json:
```
sudo docker-compose exec backend python manage.py load_data --path 'recipes/data/tags.json'
docker-compose exec backend python manage.py load_data --path 'recipes/data/ingredients.json'
```

## Автор:
Никита Палкин