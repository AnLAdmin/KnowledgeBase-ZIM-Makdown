# Setup
Created Freitag 28 Februar 2020

The setup was done with the creation of the Django project.

The following code pieces in the settings.py are needed:
```python3
INSTALLED_APPS = [
    ...
    'django.contrib.auth',  #Core authentication framework and its default models.
    'django.contrib.contenttypes',  #Django content type system (allows permissions to be associated with models).
    ....

MIDDLEWARE = [
    ...
    'django.contrib.sessions.middleware.SessionMiddleware',  #Manages sessions across requests
    ...
    'django.contrib.auth.middleware.AuthenticationMiddleware',  #Associates users with requests using sessions.
    ....
```


URL
---
Add Django default athentication views/urls to the projects urls.py (<project repository>/<project>/urls.py)
```python3
urlpatterns = [
    ...
    path('accounts/', include('django.contrib.auth.urls')),
    ...
]

```


Enable authentication
---------------------
That authentication takes effect add decorators [@login_required](https://docs.djangoproject.com/en/3.0/topics/auth/default/#django.contrib.auth.decorators.login_required) or [@permission_required('<permission>')](https://docs.djangoproject.com/en/3.0/topics/auth/default/#the-permission-required-decorator) (if generic view use appropriate mixin)  to the views which you want authenticated. This will prompt the [login page](./Login.md) if not already logged in.

### Example
Access for all groups:
```python3
@login_required
def index(request):
	...
```

or access to members of a specific group:
```python3
@@permission_required('app.list')
def list_something:
	...
```


Login template
--------------
Create [login template](./Login.md).

