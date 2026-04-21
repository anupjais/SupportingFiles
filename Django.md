## Resources 
```
https://pypi.org/project/uv/
```
-   Anup@123
```
https://www.djangoproject.com/download/
```
```
https://jinja.palletsprojects.com/en/stable/
```

## Django project Setups
```
pip install uv
```
-  Install it
```
uv venv
```
```
source .venv/bin/activate
```
-  Activate with: For mac
```
uv pip install Django 
```
```
django-admin startproject chaiAurChai
```
```
cd chaiAurChai
```
## To run
```
python manage.py runserver
```
### or 
```
python manage.py runserver 8001
```


# Essentials
- Create "templates" and "static" folders inside the project
- templates: for HTML
- static: for CSS, JS


# Settings
```
import os
```
```
STATICFILES_DIRS = [os.path.join(BASE_DIR, 'static')]
```
- below the STATIC_URL
```
add templates in TEMPLATES like "'DIRS': ['templates'],"
```

- views.py
```
def home(request):
    # return HttpResponse("Good Evening! You're at Home")
    return render(request, 'website/index.html')
```

: these are the things will execute




### Insert Tailwind with Django
```
uv pip install django-tailwind
```
```
python -m ensurepip --upgrade
```
### or
```
python -m pip install --upgrade pip
```
```
uv pip install 'django-tailwind[reload]'
```
:  for the hot reload
### or
```
pip install 'django-tailwind[reload]'
```
 : either change the theme name or enter for defalt

```
python manage.py tailwind init
```
```
python manage.py tailwind install
```
```
python manage.py tailwind start
```
- In other Tab of Terminal
```
python manage.py runserver
```
###  or
```
python manage.py runserver 8001
```



## Warnning 
```
python manage.py migrate
```
```
python manage.py runserver
```
### or
```
python manage.py runserver 8001
```


## To enable/create super-user
```
python manage.py createsuperuser
```
### Example
```
Username (leave blank to use 'anupjaiswal'): Mistri
Email address: examsample0@gmail.com
Password: 
Password (again):
```

## Images
```
python -m pip install Pillow
```
- For the utilities
```
pip freeze > requirements.txt 
```


## Migrations
```
python manage.py makemigrations chai
```
```
python manage.py migrate
```
