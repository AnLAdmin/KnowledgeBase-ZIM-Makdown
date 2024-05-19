# Configuration
Created Dienstag 03 März 2020

[Source](https://docs.djangoproject.com/en/3.0/topics/templates/#configuration)

Global
------
This setups a project global tmplates directory.
Add os.path.join(BASE_DIR, '<project>/templates') to DIRS []:
```python3
'DIRS': [os.path.join(BASE_DIR, '<project>/templates')],
```

This puts the projects templates directory into the same directory as the settings.py file. By Django default the templates directory is normally in the project repository root. *But I don't want to have program code in the project root*.

