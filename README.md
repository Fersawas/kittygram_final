# TASKS
## Описание проекта
Проект kittygram позволяет создавать посты с котами, отмечать их достижения. Созданы docker образы, с помощью которых можно запустить проект.
### Содержанеие

- [Технологии](#tech)
- [Начало работы](#begining)
- [Запуск через докер](#docker)
- [Комнада проекта](#team)

## <a name="tech">Технологии</a>

- [Django](https://www.djangoproject.com/)
- [Django REST](https://www.django-rest-framework.org/)

## <a name="begining">Начало работы</a>

### Начало работы

Активируйте вирутальное окржуние:

```
python -m venv venv
```

### Установка зависимостей

Активируйте виртуальное окружение

```
source venv/sqripts/activate
```

Установите зависимости из файла *requirements.txt*:

```
pip install -r requirements.txt
```

## <a name="docker">Запуск через docker</a>

Зайти в корневую директорию. 
Запустить docker файл:

```
docker compose -f docker-compose.yml up -d
```

Соберите и скопируйте статику

```
docker compose -f docker-compose.yml exec backend python manage.py collect_static
docker compose -f docker-compose.yml exec backend cp -r /app/static/. /backend_static/static/ 
```

Примение миграции и заполните базу данных

```
docker compose -f docker-compose.yml exec backend python manage.py migrate
docker compose -f docker-compose.yml exec backend python manage.py csv_to_sql
```

Ваш сайт доступен по адресу /localhost:8080/

Если захотите отключить локальный сервер
Введите следующие команды

```
docker compose -f docker-compose.yml down -v
```

## <a name="team">Команда проектка</a>

- Паршин Денис - разработчик
