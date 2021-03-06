# Docker Setup

Use this guide if you want to use Docker in your project.

> Built with Docker v18.03.0-ce.

## Getting Started

Update the environment variables in *docker-compose.yml*, and then build the images and spin up the containers:

```sh
$ docker-compose up -d --build
```

Create the database:

```sh
$ docker-compose run web python manage.py create_db
$ docker-compose run web python manage.py db init
$ docker-compose run web python manage.py db migrate
$ docker-compose run web python manage.py create_admin
$ docker-compose run web python manage.py create_data
```

Access the application at the address [http://localhost:5002/](http://localhost:5002/)

### Testing

Test without coverage:

```sh
$ docker-compose run web python manage.py test
```

Test with coverage:

```sh
$ docker-compose run web python manage.py cov
```

Lint:

```sh
$ docker-compose run web flake8 project
```
