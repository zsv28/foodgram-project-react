[![Foodgram workflow](https://github.com/zsv28/foodgram-project-react/actions/workflows/workflow_foodgram.yml/badge.svg)]

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&size=22&pause=1000&color=F7A113&background=FFD9EA00&width=435&lines=Foodgram+-+%D0%BF%D1%80%D0%BE%D0%B4%D1%83%D0%BA%D1%82%D0%BE%D0%B2%D1%8B%D0%B9+%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D0%BD%D0%B8%D0%BA)](https://git.io/typing-svg)
 
Cайт для публикации кулинарных рецептов.\
Вы можете публиковать, редактировать и удалять свои рецепты, так же просматривать рецепты
добавленные другими пользователями.\
Есть возможность добавлять рецепты в избранное, подписываться на других пользователей
публикующих свои рецепты на сайте.\
Есть выгрузка в файл ингредиентов с необходимым количеством для приготовления блюда.
### Технолонии
[![Python](https://img.shields.io/badge/-Python-464646?style=flat-square&logo=Python)](https://www.python.org/)
[![Django](https://img.shields.io/badge/-Django-464646?style=flat-square&logo=Django)](https://www.djangoproject.com/)
[![Django REST Framework](https://img.shields.io/badge/-Django%20REST%20Framework-464646?style=flat-square&logo=Django%20REST%20Framework)](https://www.django-rest-framework.org/)
[![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-464646?style=flat-square&logo=PostgreSQL)](https://www.postgresql.org/)
[![Nginx](https://img.shields.io/badge/-NGINX-464646?style=flat-square&logo=NGINX)](https://nginx.org/ru/)
[![gunicorn](https://img.shields.io/badge/-gunicorn-464646?style=flat-square&logo=gunicorn)](https://gunicorn.org/)
[![docker](https://img.shields.io/badge/-Docker-464646?style=flat-square&logo=docker)](https://www.docker.com/)

- Python 3.9
- Django 3.2.15
- Django Rest Framework 3.14.0
- Djoser 2.1.0

### Доступный функционал

- Аутентификация реализована с помощью стандартного модуля DRF - Authtoken.
- У неаутентифицированных пользователей доступ к API только на уровне чтения.
- Создание объектов разрешено только аутентифицированным пользователям.На прочий фунционал наложено ограничение в виде административных ролей и авторства.
- Управление пользователями.
- Возможность получения подробной информации о себе и ее редактирование.
- Возможность подписаться на других пользователей и отписаться от них.
- Получение списка всех тегов и ингредиентов.
- Получение списка всех рецептов, их добавление.Получение, обновление и удаление конкретного рецепта.
- Возможность добавить рецепт в избранное.
- Возможность добавить рецепт в список покупок.
- Возможность скачать список покупок в PDF формате.
- Фильтрация по полям.

#### Локальный запуск проекта

- Склонировать репозиторий:

```bash
   git clone git@github.com:zsv28/foodgram-project-react.git
```


В папке с проектом создать и активировать виртуальное окружение:

Команда для установки виртуального окружения на Mac или Linux:

```bash
   python3 -m venv env
   source env/bin/activate
```

Команда для Windows:

```bash
   python -m venv venv
   source venv/Scripts/activate
```

- Перейти в директорию infra:

```bash
   cd infra
```

- Создать файл .env по образцу:

```bash
   cp .env.example .env
```

- Выполнить команду для доступа к документации:

```bash
   docker compose up 
```

Установить зависимости из файла requirements.txt:

```bash
   cd ..
   cd backend
   pip install -r requirements.txt
```

```bash
   python manage.py migrate
```

Заполнить базу тестовыми данными об ингредиентах:

```bash
   python manage.py load_json_data
```

Создать суперпользователя, если необходимо:

```bash
python manage.py createsuperuser
```

- Запустить локальный сервер:

```bash
   python manage.py runserver
```


### Запустить проект локально с помощью Doker:
Создать backend, frontend образы
```
docker build -t <название образа> .
```
Запушить образы в Doker
```
docker push <название образа>
```
Перейти в папку infra
```
cd infra
```
Запустите контейнеры docker-compose командой
```
docker compose up --build
```
Выполните миграции
```
docker compose exec backend python manage.py migrate
```
Создайте суперпользователя
```
docker compose exec backend python manage.py createsuperuser
```
Соберите статику
```
docker compose exec backend python manage.py collectstatic --no-input
```
Заполните базу ингредиентами и тегами
```
docker compose exec backend python manage.py load_json_data
```

### .env-файл
```
SECRET_KEY='' - укажите секретный ключ
DB_ENGINE= - укажите какая БД используться
DB_NAME= - название БД
POSTGRES_USER=  - Логин для подключения к БД
POSTGRES_PASSWORD= - Пароль для подключения к БД
DB_HOST=  - Название контейнера
DB_PORT= - Порт для подключени к БД
ALLOWED_HOSTS= - Хосты
DEBUG= - Режим дегаб
```

### secrets GitHub для выгрузки на сервер через workflow
```
DOCKER_USERNAME=<имя пользователя DockerHub>
DOCKER_PASSWORD=<пароль от DockerHub>

USER=<username для подключения к удаленному серверу>
HOST=<ip сервера>
PASSPHRASE=<пароль для сервера, если он установлен>
SSH_KEY=<ваш приватный SSH-ключ (для получения команда: cat ~/.ssh/id_rsa)>

TELEGRAM_TO=<id вашего Телеграм-аккаунта>
TELEGRAM_TOKEN=<токен вашего бота>
```

### Проект доступен по адресу
https://thefoodgram.ddns.net/

### Данные для пробного доступа
```
Admin - admin@admin.ru
        admin12345678

User - test@test.ru
       test12345678
```

[![Github](https://icons8.ru/icon/fmFqQmR0UdsR/github)](https://github.com/zsv28)

