#Get start with django
I have long time no work with django, because i have a lovely toy `flask`. but
 for get a job, i have to learn something about django today! I will follow the tutorial from [django] documentation.
 
###Part 1
There are few command very useful, so list below.

* 1.Run `django-admin startproject mysite` to create a project.
* 2.Run `python manage.py runserver` to run the web server.
* 3.Run `python manage.py startapp polls` to createa a app.

####Write my first view

polls/views.py

```
from django.http import HttpResponse


def index(request):
    return HttpResponse("Hello, world. You're at the polls index.")

```

####Map the url to view function
In the polls/urls.py file include following code.

```
from django.conf.urls import url, include

from . import views

urlpatterns = [
    url(r'^$', views.index, name='index'),
]
```
####Run it & test

```
python manage.py runserver
```

###Part 2

There are many file inside the project, I just need to know the below item for now.

* 1.Database setup inside of `mysite/settings.py`
* 2.Run the `python manage.py migrate`
* 3.Create models by Django ORM
* 4.Tell the project that the polls app is installed.
* 5.Run `python manage.py makemigrations polls`
* 6.Run `python manage.py migrate`


By put `polls.apps.PollsConfig` on the `INSTALLED_APPS` list, and then the django project will know it. To test your models work as expect,you can play with shell.

```
python manage.py shell
```


[django]:https://docs.djangoproject.com/en/1.9/intro/tutorial01/
