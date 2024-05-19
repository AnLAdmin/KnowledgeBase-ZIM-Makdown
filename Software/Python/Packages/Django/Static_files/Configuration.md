# Configuration
Created Dienstag 03 März 2020

settings.py
-----------
Include **django.contrib.staticfiles** in INSTALLED_APPS. -> By default included.
Add STATIC_URL = '<relative path to static files on a web server>'
-> E.g. STATIC_URL = '/static/'


### Global files
Add to settings.py:
```python
STATICFILES_DIRS = [
    os.path.join(BASE_DIR, "<relativedir name for static files>"),
    '<absolut dir name for static files>',
]
```

-> This uses [STATICFILES_FINDERS.](https://docs.djangoproject.com/en/3.0/ref/settings/#std:setting-STATICFILES_FINDERS) Desciption for [STATICFILES_DIRS](https://docs.djangoproject.com/en/3.0/ref/settings/#staticfiles-dirs-prefixes).

#### Attention
__Do not create app directories in this dierctories. This are global and not specific to an app.__ (my advice)

