# API Gateway

Django REST Framework API gateway for the DADM project. The project currently
contains the Django foundation and admin site; application API routes will be
added as they are implemented.

## Table of contents

- [API Gateway](#api-gateway)
  - [Table of contents](#table-of-contents)
  - [Requirements](#requirements)
  - [Setup](#setup)
  - [Database](#database)
  - [Run the project](#run-the-project)
  - [Tests and checks](#tests-and-checks)

## Requirements

- Python 3.13 or newer
- [uv](https://docs.astral.sh/uv/)

## Setup

Install the locked dependencies from the project directory:

```bash
uv sync
```

The settings read `SECRET_KEY` and `DEBUG` from the process environment. Set
them before running Django commands:

```bash
export SECRET_KEY='replace-this-with-a-local-secret'
export DEBUG=True
```

`SECRET_KEY` must be kept private and should be replaced with a secure value
outside local development. `.env.example` lists the available settings, but
the variables must be exported or loaded by your shell because Django reads
them from the process environment.

## Database

The development database is SQLite and is stored in `db.sqlite3`. Apply the
Django migrations with:

```bash
uv run python manage.py migrate
```

Create an admin user when needed:

```bash
uv run python manage.py createsuperuser
```

## Run the project

Start the development server with:

```bash
uv run python manage.py runserver
```

Open the admin site at <http://127.0.0.1:8000/admin/>.

## Tests and checks

Run the Django test suite:

```bash
uv run python manage.py test
```

Run Django's project checks:

```bash
uv run python manage.py check
```
