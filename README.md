docker-compose up -d --build;
docker-compose exec web python manage.py migrate;
docker-compose exec web python manage.py createsuperuser;
# It works on port 8000
