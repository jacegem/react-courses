# Tutorial: Django REST with React (Django 2.0 and a sprinkle of testing)

- https://www.valentinog.com/blog/tutorial-api-django-rest-react/

A practical (opinionated) introduction to using Django REST with React. Featuring Django 2.0!

## What you will learn

In the following tutorial you'll learn:

- how to build a simple Django REST API
- how to structure a Django project with Rect

What we will build?

I love **marketing automation** (I'm building a lightweight Drip clone for a client)

And in this project we'll build a **simple API for listing and storing leads**

## Requirements

To follow along with the tutorial you should have:

- a basic understanding of **Python** and **Django**
- a basic understanding of **Javascript ES6** and **React**
- a newer version of Node.js installed on your system
- [pipenv](http://pipenv.readthedocs.io/en/latest/) installed on your system

Ready? Let's get started!

## Setting up a Python virtual environment, and the project

What's your favorite tool for managing Python virtual environments?

I felt in love with pipenv. I like its resemblance with NPM.

Let's start the project by createing a new directory:

```shell
mkdir django-drf-react-quickstart && cd $_
```

Next up create a new virtual environment by running:

```shell
pip install pipenv
pipenv --three
```

Now it's time to pull our depedencies in.

install Django and [Django REST framwork](http://www.django-rest-framework.org/) by running:

```shell
pipenv install django djangorestframework
```

When the installation ends spawn a shell within the virtual environment by running:

```shell
pipenv shell
```

A this point you're ready to create a new Django project:

```shell
django-admin startproject project
```

Now we can start building our first Django app: a simple API for listing and storing leads.

## Building a Django application

A Django project consists of many applications. Each application should ideally do one thing.

Django applications are modular and reusable. For example: I can create a leads application for creating and listing leads.

If another project needs the same app I can install leads from the package manager and that's all.

I suggest reading [How to write reusable apps](https://docs.djangoproject.com/en/2.0/intro/reusable-apps/) and watching [DjangoCon 2008: Reusable Apps](https://www.youtube.com/watch?v=A-S0tqpPga4&feature=youtu.be) to learn about app best practices.

To create a new application in Django you would run:

```shell
django-admin startapp app_name
```

To create the leads app move inside the project folder:

```shell
cd project
```

and initalize the app:

```shell
django-admin startapp leads
```

Open up `./project/settings.py` and add the app in INSTALLED_APPS:

```python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'leads', # add the leads app
]
```

So far so good!

In the next section we'll add our first model.

## Creating a Django model

With the app in place it's time to create our firt model.

A model is an object representing your table's data.

Almost every web framework has the concept of models. Django makes no exception. A Django model may have one or more field: each filed is a column in you table. Before moving forward let's define our requirements for the lead application.

First we need a Lead model.

Since I'm collecting leads I can think of a Lead model make of the following fields:

- a name
- an email
- a message











