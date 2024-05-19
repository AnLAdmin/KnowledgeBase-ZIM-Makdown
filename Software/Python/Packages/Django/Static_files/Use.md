# Use
Created Dienstag 03 März 2020

[Source](https://docs.djangoproject.com/en/3.0/howto/static-files/)

Use in template
---------------
Add somewhere at the top of a template:
```html
{% load static %}
```


### Link to the  resource
{% static '<app name><path to resource>' %}

#### Examples

##### CSS
```html
<link rel="stylesheet" type="text/css" href="{% static 'Inventory/css/main.css' %}" media="screen,projection" />
```


##### Picture
```html
<img src="{% static "my_app/example.jpg" %}" alt="My image">
```


### Attention
Create a <app name> subdirectory in the directory static for the app.

