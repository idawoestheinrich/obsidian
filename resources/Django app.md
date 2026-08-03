## Creating a project
```shell
django-admin startproject mysite djangotutorial
```
That creates
```shell
djangotutorial/
    manage.py
    mysite/
        __init__.py
        settings.py
        urls.py
        asgi.py
        wsgi.py
```
- `manage.py`: A command-line utility that lets you interact with this Django project in various ways. You can read all the details about `manage.py` in [django-admin and manage.py](https://docs.djangoproject.com/en/6.0/ref/django-admin/).
- `mysite/`: A directory that is the actual Python package for your project. Its name is the Python package name you’ll need to use to import anything inside it (e.g. `mysite.urls`).
- `mysite/__init__.py`: An empty file that tells Python that this directory should be considered a Python package. If you’re a Python beginner, read [more about packages](https://docs.python.org/3/tutorial/modules.html#tut-packages "(in Python v3.14)") in the official Python docs.
- `mysite/settings.py`: Settings/configuration for this Django project. [Django settings](https://docs.djangoproject.com/en/6.0/topics/settings/) will tell you all about how settings work.
- `mysite/urls.py`: The URL declarations for this Django project; a “table of contents” of your Django-powered site. You can read more about URLs in [URL dispatcher](https://docs.djangoproject.com/en/6.0/topics/http/urls/).
- `mysite/asgi.py`: An entry-point for ASGI-compatible web servers to serve your project. See [How to deploy with ASGI](https://docs.djangoproject.com/en/6.0/howto/deployment/asgi/) for more details.
- `mysite/wsgi.py`: An entry-point for WSGI-compatible web servers to serve your project. See [How to deploy with WSGI](https://docs.djangoproject.com/en/6.0/howto/deployment/wsgi/) for more details


# Making a polls app 
[link](https://docs.djangoproject.com/en/6.0/intro/tutorial02/)

- Change your models (in `models.py`).
- Run [`python manage.py makemigrations`](https://docs.djangoproject.com/en/6.0/ref/django-admin/#django-admin-makemigrations) to create migrations for those changes
- Run [`python manage.py migrate`](https://docs.djangoproject.com/en/6.0/ref/django-admin/#django-admin-migrate) to apply those changes to the database.

[[Test-driven development (TDD)]]
As long as your tests are sensibly arranged, they won’t become unmanageable. Good rules-of-thumb include having:

- a separate `TestClass` for each model or view
    
- a separate test method for each set of conditions you want to test
    
- test method names that describe their function

# Online Tutorials

#### Django 
- direct to virtual envy
- admin startproject

- [templates django](https://github.com/django/django/tree/main/django/contrib/admin/templates)