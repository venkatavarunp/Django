
# Django
## New Project
Create a new project using the command 
```python
django-admin startproject <projectname>
```

## Django Apps
Subsets of main project
```python
python manage.py startapp <appname>
```

## URL Routing
### urls.py of app 
```python
from django.urls import path 
from . import views
urlpatterns = [
    path('',views.index,name='index'),
    path('greet',views.greet,name='greet')
]
```
### views.py of app 
```python
from django.shortcuts import render
from django.http import HttpResponse

def index(request):
    return HttpResponse('Welcome')

def greet(request):
    return HttpResponse('Greet Page')
```
### urls.py of project
```python
from django.contrib import admin
from django.urls import path,include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('',include("app.urls"))
]

```
## Django Template Language
