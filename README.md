# Django Tailwind Template

Minimal Django project setup template.

## Features

- Django 5.1
- Uses Poetry for dependency management
- Includes TailwindCSS set up and a basic template to extend

## Environment set up

Create a `.env` file by copying the `.env.example` contents and add the
corresponding values.

```plaintext
APP_DEBUG=false
APP_ALLOWED_HOST=https://example.com
```

## Set up

Create an app:

```sh
poetry shell
python manage.py startapp myapp
```

Add the app to the `INSTALLED_APPS` in `core/settings.py`:

```python
INSTALLED_APPS = [
  ...,
  myapp,
]
```

Create your templates in `myapp/templates/`, then extend the provided layout:

```djangohtml
{% extends 'layout.html' %}

{% block title %}My App Title{% endblock title %}

{% block content %}
<h1 class="text-2xl text-blue-600 font-semibold">Hello, world!</h1>
{% endblock content %}
```

## Running the app

For the Django server, open a terminal and run:

```sh
poetry shell
python manage.py runserver
```

To build the css assets, run:

```sh
yarn run dev
```

For production ready assets:

```sh
yarn run build
```
