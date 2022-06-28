# template-docker-dj-pgsql-nginx-staticfile
This project is a template for Docker, Django, PosgreSQL, NGINX

docker-compose up --build
docker-compose exec web python manage.py migrate --noinput

docker-compose -f docker-compose.prod.yml up --build
docker-compose -f docker-compose.prod.yml exec web python manage.py migrate --noinput

