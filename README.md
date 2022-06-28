
# Template-docker-dj-pgsql-nginx-staticfile

This project is a template for Docker, Django, PosgreSQL, NGINX for both local/dev and prod.


## Run Locally

Clone the project

```bash
  git clone https://github.com/akshay98322/template-docker-dj-pgsql-nginx-staticfile.git
```
Go to the project directory

```bash
  cd template-docker-dj-pgsql-nginx-staticfile
```

To run this project, you will need to rename the .env.dev-sample to .env.dev and add the environment variables to your .env.dev file.

Start the server

```bash
  docker-compose up --build
```

Migrate the tables

```bash
  docker-compose exec web python manage.py migrate --noinput
```

Check at http://localhost:8000/ for the app

Stop the server

```bash
  docker-compose down
```

## Run the prod build Locally

To run the prod build, you will need to rename the .env.prod-sample to .env.prod and add the environment variables to your .env.prod file.

Start the server

```bash
  docker-compose -f docker-compose.prod.yml up --build
```

Migrate the tables

```bash
  docker-compose -f docker-compose.prod.yml exec web python manage.py migrate --noinput
```

Collect the static files

```bash
  docker-compose -f docker-compose.prod.yml exec web python manage.py collectstatic --no-input --clear
```
Check at http://localhost:1337/ for the app

Stop the server

```bash
  docker-compose -f docker-compose.prod.yml down
```
