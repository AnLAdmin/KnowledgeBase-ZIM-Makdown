# Logout
Created Mittwoch 26 Februar 2020

[Source](https://docs.djangoproject.com/en/3.0/topics/auth/default/#django.contrib.auth.views.LogoutView)
Works without additional code or template. Shows the Django admin sites logged out page.

Customize
---------
Create a **logged_out.html** template in the directory **registration **of the projects **templates** directory.

### Example
```html
{% extends "Inventory/master.html" %}

{% block title %}{{ block.super }} - Books{% endblock %}

{% block content %}

<p>You logged out!</p>

{% endblock %}
```


