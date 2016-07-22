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

