# djangoTutorial
![django/python](./images/python_django%20.png)

A tutorial of a fully developed back end from inception through deployment using **Django** and **Python**.

## This repo is part of a series of tutorials, and here are the common features for all my tutorials

### Navigation is set to the side with the clickable links moving you down the page through the tutorial

![Nav Example](./images/django_nav.png) 

### Code snippets are highlighted in blue for easy copy/paste

code example

![Code Example](./images/python_code.png) 

(typical presentation of python code in README.md)

```python
def item_delete(request, pk):
    item = Item.objects.get(pk=pk)
    parent_id = item.todo.pk
    item.delete()
    return redirect('todo_detail', pk = parent_id)
```
### Links to supporting documents are in red within the paragraph text

![Link Example](./images/embed_link.png)

## Use this *checklist* as a quick reference for Django Build sequencial steps 
(If you copy this checklist into the issues tab of your repo, the checkboxes are clickable for easy tracking of progress)

### Setup

- [ ] Make a directory for the project
- [ ] Install python3 and virtual environment with `brew install python pipenv`
- [ ] Run `pipenv install django` and `pipenv install psycopg2-binary` to create django application with PostgreSQL
- [ ] Run `pipenv run django-admin startproject <project name> .` to initialize the project
- [ ] Start the virtual environment with `pipenv shell`
- [ ] Create the application inside the project with `django-admin startapp <application name>`
- [ ] Open PostgreSQL with `psql -d postgres`
- [ ] Create the **database**, **user**, **password**, and **privileges** for the application
- [ ] Update `settings.py` to reflect the current database
- [ ] `python3 manage.py runserver` to check everything has been installed correctly!

### Models & Admin

- [ ] Make Models in `models.py` with *Primary Key* and *Foreign Key* Relationships
- [ ] Run `python3 manage.py makemigrations` to connect the Models to the database
- [ ] Run `python3 manage.py migrate` to copy the data over
- [ ] Create a *superuser* for the admin panel `python3 manage.py createsuperuser`
- [ ] Register the Models in `admin.py`
- [ ] Visit [localhost](http://localhost:8000/admin/) to populate local database

### CRUD in Django views

- [ ] Import Models in `views.py` 
- [ ] Create python methods for *list*, *detail*, *create*, *update*, and *delete* 
- [ ] Add `urls.py` to the **Application** directory
- [ ] Create *urlpatterns* paths for all python methods
- [ ] Add `forms.py` to the **Application** directory and create ModelForms
- [ ] Add `templates` to the Application directory 
- [ ] Create *html* pages for *base* along with *list*, *detail*, and *form* for each Model
- [ ] Add the *includes* path to `urls.py` in the **Project** directory
- [ ] Update all *html* pages to display data from the database
- [ ] Connect Stylesheet and add CSS to Django views

### Deploy

- [ ] Install dependencies `pipenv install django-cors-headers gunicorn whitenoise dj-database-url django-heroku python-decouple`
- [ ] Create `requirements.txt` from virtual environment by running `pip freeze > requirements.txt`
- [ ] Create `Procfile` in the **Root** directory and add `web: gunicorn <project name>.wsgi` to it
- [ ] Add *cors* and adjust the *secret_key* in `settings.py`
- [ ] Run `heroku create honeydo-app` to create the Heroku copy of your application
- [ ] Run `heroku addons:create heroku-postgresql:hobby-dev` to connect the database 
- [ ] Upload to Heroku `git push heroku master`
- [ ] Migrate the database to Heroku `heroku run python manage.py migrate`
- [ ] Open the application! `heroku open`

## Final Notes
All tutorials are built with **HTML** and **CSS**

Please submit bugs and problems via the *issues* tab in this repo and feel free to browse other tutorials and content
 on my [website](https://spiano.dev).
