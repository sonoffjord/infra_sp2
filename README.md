# YaMDB
### Описание
Проект YAMDb собирает отзывы пользователей на произведения.

Произведения делятся на категории: «Книги», «Фильмы», «Музыка».

### Как развернуть проект
- git clone https://github.com/sonoffjord/infra_sp2.git
- python -m venv venv
- source venv/bin/activate
- pip install -r requirements.txt
- python manage.py migrate
- python manage.py createsuperuser
- python manage.py runserver

Убедитесь что локально все работает, затем
  
- Создайте файл .env со значениями:
  
  DB_ENGINE=django.db.backends.postgresql 
  
  DB_NAME=postgres 
  
  POSTGRES_USER=postgres 
  
  POSTGRES_PASSWORD=postgres 
  
  DB_HOST=db 
  
  DB_PORT=5432 
  
  EMAIL_HOST_PASSWORD=<Ваш пароль от почты>
  

- Запустите Docker: 
  
  #### sudo docker-compose up

- Выполните миграции внутри докера:
  
  #### sudo docker-compose exec web python manage.py migrate --noinput
- Создайте суперюзера внутри докера: 
  
  #### sudo docker-compose exec web python manage.py createsuperuser
- Соберите всю статику внутри докера:
  
  #### sudo docker-compose exec web python manage.py collectstatic --no-input
- Загрузите тестовые данные 
  
  #### sudo docker-compose exec web python manage.py loaddata fixtures.json
