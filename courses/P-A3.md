### [A3-DJANGO TUTORIAL - W3SCHOOLS](/courses/A3.md)

+INTRODUCTION

<details>
  <summary>A1. Introduction </summary>

Django follows the MVT design pattern (Model View Template).

- Model - The data you want to present, usually data from a database.
- View - A request handler that returns the relevant template and content - based on the request from the user.
- Template - A text file (like an HTML file) containing the layout of the web page, with logic on how to display the data.

Model <br>

The model provides data from the database.

- In Django, the data is delivered as an Object Relational Mapping (ORM), which is a technique designed to make it easier to work with databases.

- The most common way to extract data from a database is SQL. One problem with SQL is that you have to have a pretty good understanding of the database structure to be able to work with it.

- Django, with ORM, makes it easier to communicate with the database, without having to write complex SQL statements.

- The models are usually located in a file called models.py.

View

- A view is a function or method that takes http requests as arguments, imports the relevant model(s), and finds out what data to send to the template, and returns the final result.

- The views are usually located in a file called views.py.

Template

- A template is a file where you describe how the result should be represented.

- Templates are often .html files, with HTML code describing the layout of a web page, but it can also be in other file formats to present other results, but we will concentrate on .html files.

- Django uses standard HTML to describe the layout, but uses Django tags to add logic.

- The templates of an application is located in a folder named templates.

```html
<h1>My Homepage</h1>

<p>My name is {{ firstname }}.</p>
```

URLs

- Django also provides a way to navigate around the different pages in a website.

- When a user requests a URL, Django decides which view it will send it to.

- This is done in a file called urls.py.

</details>

<details>
  <summary>A2. Install Python, pip and Venv </summary>

Download Python:

```py
https://www.python.org/
```

Check for Python Version:

```py
python --version
```

```py
# Python 3.9.12
```

Install pip:

```py
https://pypi.org/project/pip/
```

Check pip version:

```py
pip --version
```

```py
# pip 21.2.4
```

Upgrade pip:

```py
python -m pip install --upgrade pip
```

Install venv and activate the virtual environment:

```py
python -m venv venv-w3django

source venv-w3django/bin/activate
```

</details>

<details>
  <summary>A3. Install Django </summary>

```py
python -m pip install Django
```

Check Django version:

```py
django-admin --version
```

```py
# 4.1.5
```

</details>

<details>
  <summary>A4. Create Django Project </summary>

```py
django-admin startproject my_tennis_club
django-admin startproject my_tennis_club .
```

run django project -

my_tennis_club/

```py
python manage.py runserver
```

```py
# System check identified no issues (0 silenced).

# You have 18 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth, contenttypes, sessions.
# Run 'python manage.py migrate' to apply them.
# January 26, 2023 - 19:26:37
# Django version 4.1.5, using settings 'my_tennis_club.settings'
# Starting development server at http://127.0.0.1:8000/
# Quit the server with CONTROL-C.
```

127.0.0.1:8000:

![001](https://user-images.githubusercontent.com/32337103/214931443-5581766b-920d-4ddb-ac99-c649421fa3d1.png)

</details>

<details>
  <summary>A5. Create Django App </summary>

my_tennis_club/

```py
python manage.py startapp members
```

</details>

<details>
  <summary>A6. Create Django View - return HttpResponse </summary>

members/views.py:

```py
from django.shortcuts import render
from django.http import HttpResponse

def members(request):
    return HttpResponse("Hello world!")
```

</details>

<details>
  <summary>A7. Create urls.py routes </summary>

my_tennis_club/members/urls.py:

```py
from django.urls import path
from . import views

urlpatterns = [
    path('members/', views.members, name='members'),
]
```

my_tennis_club/my_tennis_club/urls.py:

```py
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('', include('members.urls')),
    path('admin/', admin.site.urls),
]
```

/my_tennis_club:

```py
python manage.py runserver
```

127.0.0.1:8000/members:

![002](https://user-images.githubusercontent.com/32337103/214957810-f91a2461-1028-4d23-bcd4-9ef782e741e4.png)

</details>

<details>
  <summary>A8. Create and load HTML Template </summary>

my_tennis_club/members/templates/myfirst.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>Hello World!</h1>
    <p>Welcome to my first Django project!</p>
  </body>
</html>
```

my_tennis_club/members/views.py:

```py
from django.http import HttpResponse
from django.template import loader

def members(request):
  template = loader.get_template('myfirst.html')
  return HttpResponse(template.render())
```

</details>

<details>
  <summary>A9. Register App in Settings </summary>

my_tennis_club/my_tennis_club/settings.py:

```py
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'members'
]
```

Run Migrations:

```py
# python manage.py makemigrations
python manage.py migrate
```

/my_tennis_club

```py
python manage.py runserver
```

127.0.0.1:8000/members:

![004](https://user-images.githubusercontent.com/32337103/214960898-da8f5076-7b10-4112-a4cd-f9d12589fc5d.png)

</details>

<details>
  <summary>A10. Create Member Model </summary>

my_tennis_club/members/models.py:

```py
from django.db import models

class Member(models.Model):
  firstname = models.CharField(max_length=255)
  lastname = models.CharField(max_length=255)
```

my_tennis_club/

```py
python manage.py makemigrations members
```

```py
python manage.py migrate
```

View SQL migrate:

```py
python manage.py sqlmigrate <model> <migration number>
python manage.py sqlmigrate members 0001
```

```py
# BEGIN;
# --
# -- Create model Member
# --
# CREATE TABLE "members_member" ("id" integer NOT NULL PRIMARY KEY AUTOINCREMENT, "firstname" varchar(255) NOT NULL, "lastname" varchar(255) NOT NULL);
# COMMIT;
```

</details>

<details>
  <summary>A11. Get and Insert Data </summary>

Enter Python Shell

```py
python manage.py shell
```

```py
# Python 3.9.13 (v3.9.13:6de2ca5339, May 17 2022, 11:37:23)
# [Clang 13.0.0 (clang-1300.0.29.30)] on darwin
# Type "help", "copyright", "credits" or "license" for more information.
# (InteractiveConsole)
# >>>
```

GET Data from Members Table (Model):

```py
>>> from members.models import Member
>>> Member.objects.all()
```

```py
# <QuerySet []>
```

POST/Add a single Data record to Members Table (Model):

```py
>>> member = Member(firstname='Emil', lastname='Refsnes')
>>> member.save()
```

View added record in Model:

```py
>>> Member.objects.all()
```

```py
# <QuerySet [<Member: Member object (1)>]>
```

```py
>>> Member.objects.all().values()
```

```py
# <QuerySet [{'id': 1, 'firstname': 'Emil', 'lastname': 'Refsnes'}]>
```

To add Multiple Records in the Model:

```py
>>> member1 = Member(firstname='Tobias', lastname='Refsnes')
>>> member2 = Member(firstname='Linus', lastname='Refsnes')
>>> member3 = Member(firstname='Lene', lastname='Refsnes')
>>> member4 = Member(firstname='Stale', lastname='Refsnes')
>>> member5 = Member(firstname='Jane', lastname='Doe')
>>> members_list = [member1, member2, member3, member4, member5]
>>> for x in members_list:
>>>   x.save()
```

View added records in Model:

```py
>>> Member.objects.all().values()
```

```py
# <QuerySet [{'id': 1, 'firstname': 'Emil', 'lastname': 'Refsnes'},
# {'id': 2, 'firstname': 'Tobias', 'lastname': 'Refsnes'},
# {'id': 3, 'firstname': 'Linus', 'lastname': 'Refsnes'},
# {'id': 4, 'firstname': 'Lene', 'lastname': 'Refsnes'},
# {'id': 5, 'firstname': 'Stale', 'lastname': 'Refsnes'},
# {'id': 6, 'firstname': 'Jane', 'lastname': 'Doe'}]>
```

</details>

<details>
  <summary>12. Update Data Records </summary>

Get the record for member at index 4, which is "Stale Refsnes":

```py
>>> from members.models import Member
>>> x = Member.objects.all()[4]
>>> x.firstname
```

```py
# 'Stale'
```

Now change the value of this record:

```py
>>> x.firstname = "Stalikken"
>>> x.save()
```

```py
>>> Member.objects.all().values()
```

```py
# <QuerySet [{'id': 1, 'firstname': 'Emil', 'lastname': 'Refsnes'},
# {'id': 2, 'firstname': 'Tobias', 'lastname': 'Refsnes'},
# {'id': 3, 'firstname': 'Linus', 'lastname': 'Refsnes'},
# {'id': 4, 'firstname': 'Lene', 'lastname': 'Refsnes'},
# {'id': 5, 'firstname': 'Stalikken', 'lastname': 'Refsnes'},
# {'id': 6, 'firstname': 'Jane', 'lastname': 'Doe'}]>
```

</details>

<details>
  <summary>13. Delete Data Records </summary>

Get the record you want to delete:

```py
>>> from members.models import Member
>>> x = Member.objects.all()[5]
>>> x.firstname
```

```py
# 'Jane'
```

Now delete the record:

```py
>>> x.delete()
```

```py
# (1, {'members.Member': 1})
```

```py
>>> Member.objects.all().values()
```

```py
# <QuerySet [{'id': 1, 'firstname': 'Emil', 'lastname': 'Refsnes'},
# {'id': 2, 'firstname': 'Tobias', 'lastname': 'Refsnes'},
# {'id': 3, 'firstname': 'Linus', 'lastname': 'Refsnes'},
# {'id': 4, 'firstname': 'Lene', 'lastname': 'Refsnes'},
# {'id': 5, 'firstname': 'Stalikken', 'lastname': 'Refsnes'}]>
```

```py
>>> exit()
```

</details>

<details>
  <summary>14. Add Fields (Columns) to Model </summary>

my_tennis_club/members/models.py:

```py
from django.db import models

class Member(models.Model):
  firstname = models.CharField(max_length=255)
  lastname = models.CharField(max_length=255)
  phone = models.IntegerField()
  joined_date = models.DateField()
```

Make Migrations:

```py
python manage.py makemigrations members
```

```py
# You are trying to add a non-nullable field 'joined_date' to members without a default; we can't do that (the database needs something to populate existing rows).
# Please select a fix:
#  1) Provide a one-off default now (will be set on all existing rows with a null value for this column)
#  2) Quit, and let me add a default in models.py
# Select an option:
```

```bs
Select option 2: allow NULL values for the two new fields.
```

my_tennis_club/members/models.py:

```py
from django.db import models

class Member(models.Model):
  firstname = models.CharField(max_length=255)
  lastname = models.CharField(max_length=255)
  phone = models.IntegerField(null=True)
  joined_date = models.DateField(null=True)
```

Make Migrations:

```py
python manage.py makemigrations members
```

```py
# Migrations for 'members':
#   members/migrations/0002_member_joined_date_member_phone.py
#     - Add field joined_date to member
#     - Add field phone to member
```

Run the migrate command:

```py
python manage.py migrate
```

```py
# Operations to perform:
#   Apply all migrations: admin, auth, contenttypes, members, sessions
# Running migrations:
#   Applying members.0002_member_joined_date_member_phone... OK
```

</details>

<details>
  <summary>15. Insert Data into updated Model </summary>

```py
python manage.py shell
```

```py
# Python 3.9.2 (tags/v3.9.2:1a79785, Feb 19 2021, 13:44:55) [MSC v.1928 64 bit (AMD64)] on win32
# Type "help", "copyright", "credits" or "license" for more information.
# (InteractiveConsole)
# >>>
```

```py
>>> from members.models import Member
>>> x = Member.objects.all()[0]
>>> x.phone = 5551234
>>> x.joined_date = '2022-01-05'
>>> x.save()
```

```py
>>> Member.objects.all().values()
```

```py
# <QuerySet [
# {'id': 1, 'firstname': 'Emil', 'lastname': 'Refsnes', 'phone': 5551234, 'joined_date': datetime.date(2022, 1, 5)},
# {'id': 2, 'firstname': 'Tobias', 'lastname': 'Refsnes', 'phone': None, 'joined_date': None},
# {'id': 3, 'firstname': 'Linus', 'lastname': 'Refsnes', 'phone': None, 'joined_date': None},
# {'id': 4, 'firstname': 'Lene', 'lastname': 'Refsnes', 'phone': None, 'joined_date': None},
# {'id': 5, 'firstname': 'Stalikken', 'lastname': 'Refsnes', 'phone': None, 'joined_date': None}]>
```

</details>

+DISPLAY TEMPLATE DATA

<details>
  <summary>16. Create All Members Page </summary>

my_tennis_club/members/templates/all_members.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>Members</h1>

    <ul>
      {% for x in mymembers %}
      <li>{{ x.firstname }} {{ x.lastname }}</li>
      {% endfor %}
    </ul>
  </body>
</html>
```

my_tennis_club/members/views.py:

```py
from django.http import HttpResponse
from django.template import loader
from .models import Member

def members(request):
  mymembers = Member.objects.all().values()
  template = loader.get_template('all_members.html')
  context = {
    'mymembers': mymembers,
  }
  return HttpResponse(template.render(context, request))
```

my_tennis_club/members/urls.py:

```py
from django.urls import path
from . import views

urlpatterns = [
    path('members/', views.members, name='members'),
]
```

my_tennis_club/

```py
python manage.py runserver
```

![004](https://user-images.githubusercontent.com/32337103/215118713-ad8cf2c0-cb2a-497d-b558-bc273b8245bc.png)

</details>

<details>
  <summary>17. Create Details Page </summary>

my_tennis_club/members/templates/details.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>{{ mymember.firstname }} {{ mymember.lastname }}</h1>

    <p>Phone: {{ mymember.phone }}</p>
    <p>Member since: {{ mymember.joined_date }}</p>

    <p>Back to <a href="/members">Members</a></p>
  </body>
</html>
```

my_tennis_club/members/templates/all_members.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>Members</h1>

    <ul>
      {% for x in mymembers %}
      <li>
        <a href="details/{{ x.id }}">{{ x.firstname }} {{ x.lastname }}</a>
      </li>
      {% endfor %}
    </ul>
  </body>
</html>
```

my_tennis_club/members/views.py:

```py
from django.http import HttpResponse
from django.template import loader
from .models import Member

def members(request):
  mymembers = Member.objects.all().values()
  template = loader.get_template('all_members.html')
  context = {
    'mymembers': mymembers,
  }
  return HttpResponse(template.render(context, request))

def details(request, id):
  mymember = Member.objects.get(id=id)
  template = loader.get_template('details.html')
  context = {
    'mymember': mymember,
  }
  return HttpResponse(template.render(context, request))
```

my_tennis_club/members/urls.py:

```py
from django.urls import path
from . import views

urlpatterns = [
    path('members/', views.members, name='members'),
    path('members/details/<int:id>', views.details, name='details'),
]
```

```py
py manage.py runserver
```

![006](https://user-images.githubusercontent.com/32337103/215122475-c5df9fb6-5c0e-4e6e-8dff-3a7078130f4c.png)

![007](https://user-images.githubusercontent.com/32337103/215122533-7600e321-0f0a-4a66-b7df-ea43fcdc6de1.png)

</details>

<details>
  <summary>18. Create Master Layout Page </summary>

my_tennis_club/members/templates/master.html:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>{% block title %}{% endblock %}</title>
  </head>
  <body>
    {% block content %} {% endblock %}
  </body>
</html>
```

my_tennis_club/members/templates/all_members.html:

```bs
{% extends "master.html" %}

{% block title %}
  My Tennis Club - List of all members
{% endblock %}


{% block content %}
  <h1>Members</h1>

  <ul>
    {% for x in mymembers %}
      <li><a href="details/{{ x.id }}">{{ x.firstname }} {{ x.lastname }}</a></li>
    {% endfor %}
  </ul>
{% endblock %}
```

my_tennis_club/members/templates/details.html:

```bs
{% extends "master.html" %}

{% block title %}
  Details about {{ mymember.firstname }} {{ mymember.lastname }}
{% endblock %}


{% block content %}
  <h1>{{ mymember.firstname }} {{ mymember.lastname }}</h1>

  <p>Phone {{ mymember.phone }}</p>
  <p>Member since: {{ mymember.joined_date }}</p>

  <p>Back to <a href="/members">Members</a></p>

{% endblock %}
```

```py
py manage.py runserver
```

![006](https://user-images.githubusercontent.com/32337103/215122475-c5df9fb6-5c0e-4e6e-8dff-3a7078130f4c.png)

![007](https://user-images.githubusercontent.com/32337103/215122533-7600e321-0f0a-4a66-b7df-ea43fcdc6de1.png)

</details>

<details>
  <summary>19. Create Main Landing Page </summary>

my_tennis_club/members/templates/main.html:

```bash
{% extends "master.html" %}

{% block title %}
  My Tennis Club
{% endblock %}


{% block content %}
  <h1>My Tennis Club</h1>

  <h3>Members</h3>

  <p>Check out all our <a href="members/">members</a></p>

{% endblock %}
```

my_tennis_club/members/views.py:

```py
from django.http import HttpResponse
from django.template import loader
from .models import Member

def members(request):
  mymembers = Member.objects.all().values()
  template = loader.get_template('all_members.html')
  context = {
    'mymembers': mymembers,
  }
  return HttpResponse(template.render(context, request))

def details(request, id):
  mymember = Member.objects.get(id=id)
  template = loader.get_template('details.html')
  context = {
    'mymember': mymember,
  }
  return HttpResponse(template.render(context, request))

def main(request):
  template = loader.get_template('main.html')
  return HttpResponse(template.render())
```

my_tennis_club/members/urls.py:

```py
from django.urls import path
from . import views

urlpatterns = [
    path('', views.main, name='main'),
    path('members/', views.members, name='members'),
    path('members/details/<int:id>', views.details, name='details'),
]
```

my_tennis_club/members/templates/all_members.html:

```bash
{% extends "master.html" %}

{% block title %}
  My Tennis Club - List of all members
{% endblock %}

{% block content %}

  <p><a href="/">HOME</a></p>

  <h1>Members</h1>

  <ul>
    {% for x in mymembers %}
      <li><a href="details/{{ x.id }}">{{ x.firstname }} {{ x.lastname }}</a></li>
    {% endfor %}
  </ul>
{% endblock %}
```

```py
py manage.py runserver
```

127.0.0.1:8000/:

![007](https://user-images.githubusercontent.com/32337103/215138505-56d25ad0-33d3-480f-8e1f-fbd0092b683c.png)

![008](https://user-images.githubusercontent.com/32337103/215138775-dd6d5698-f1fa-4b48-b117-83e3119df5d2.png)

</details>

<details>
  <summary>20. Customize the 404 Template Page </summary>

- Important: When DEBUG = False, Django requires you to specify the hosts you will allow this Django project to run from.

- In production, this should be replaced with a proper domain name:

ALLOWED_HOSTS = ['yourdomain.com']

- Django will look for a file named 404.html in the templates folder, and display it when there is a 404 error.

- If no such file exists, Django shows the "Not Found" page.

- To customize this message, all you have to do is to create a file in the templates folder and name it 404.html, and fill it with write whatever you want.

my_tennis_club/my_tennis_club/settings.py:

```py
# SECURITY WARNING: don't run with debug turned on in production!
DEBUG = False

ALLOWED_HOSTS = ['*']
```

my_tennis_club/members/templates/404.html:

```html
<!DOCTYPE html>
<html>
  <title>Wrong address</title>
  <body>
    <h1>Ooops!</h1>

    <h2>I cannot find the file you requested!</h2>
  </body>
</html>
```

![008](https://user-images.githubusercontent.com/32337103/215175543-4b34095c-2a20-43f7-9fd9-3ecbcc83f620.png)

</details>

<details>
  <summary>21. Add Django Test View </summary>

my_tennis_club/members/views.py:

```py
from django.http import HttpResponse
from django.template import loader
from .models import Member

def members(request):
  mymembers = Member.objects.all().values()
  template = loader.get_template('all_members.html')
  context = {
    'mymembers': mymembers,
  }
  return HttpResponse(template.render(context, request))

def details(request, id):
  mymember = Member.objects.get(id=id)
  template = loader.get_template('details.html')
  context = {
    'mymember': mymember,
  }
  return HttpResponse(template.render(context, request))

def main(request):
  template = loader.get_template('main.html')
  return HttpResponse(template.render())

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'fruits': ['Apple', 'Banana', 'Cherry'],
  }
  return HttpResponse(template.render(context, request))
```

my_tennis_club/members/urls.py:

```py
from django.urls import path
from . import views

urlpatterns = [
    path('', views.main, name='main'),
    path('members/', views.members, name='members'),
    path('members/details/<int:id>', views.details, name='details'),
    path('testing/', views.testing, name='testing'),
]
```

my_tennis_club/members/templates/template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    {% for x in fruits %}
    <h1>{{ x }}</h1>
    {% endfor %}

    <p>In views.py you can see what the fruits variable looks like.</p>
  </body>
</html>
```

/my_tennis_club

```py
python manage.py runserver
```

127.0.0.1:8000/testing/:

![009](https://user-images.githubusercontent.com/32337103/215180047-35033aa8-cbaa-4063-9344-c1e9580eabf0.png)

</details>

+DJANGO ADMIN

<details>
  <summary>22. Introduction to Django Admin </summary>

```py
py manage.py runserver
```

my_tennis_club/my_tennis_club/urls.py:

```py
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('', include('members.urls')),
    path('admin/', admin.site.urls),
]
```

127.0.0.1:8000/admin/:

![010](https://user-images.githubusercontent.com/32337103/215181307-965a93c3-1826-4fbb-bd20-fa431138fd49.png)

Django Admin - Create User

```py
python manage.py createsuperuser
```

```py
# Username: admin
# Email address: admin@gmail.com
# Password:
# Password (again):
# This password is too short. It must contain at least 8 characters.
# This password is too common.
# This password is entirely numeric.
# Bypass password validation and create user anyway? [y/N]: y

# Superuser created successfully.
```

```py
python manage.py runserver
```

127.0.0.1:8000/admin/:

![010](https://user-images.githubusercontent.com/32337103/215181307-965a93c3-1826-4fbb-bd20-fa431138fd49.png)

![011](https://user-images.githubusercontent.com/32337103/215182500-255292f3-54c8-4952-a79c-9ba658ac8a82.png)

</details>

<details>
  <summary>23. Django Admin - Include Member Model </summary>

- The Members model is missing, as it should be, you have to tell Django which models that should be visible in the admin interface.

- This is done in a file called admin.py, and is located in your app's folder, which in our case is the members folder.

my_tennis_club/members/admin.py:

```py
from django.contrib import admin
from .models import Member

# Register your models here.
admin.site.register(Member)
```

127.0.0.1:8000/admin/:

![011](https://user-images.githubusercontent.com/32337103/215183560-c1d9f4e8-409e-48e9-b564-da01788c9dbd.png)

![012](https://user-images.githubusercontent.com/32337103/215183631-c7dc8b78-bb9e-41ce-8882-1ad9b3c74179.png)

</details>

<details>
  <summary>24. Django Admin - Set Fields to Display </summary>

Make the List Display More Reader-Friendly.

- When you display a Model as a list, Django displays each record as the string representation of the record object, which in our case is "Member object (1)", "Member object(2)" etc.

To change this to a more reader-friendly format, we have two choices:

- Change the string representation function, _str_() of the Member Model.
- Set the list_details property of the Member Model.

To Change the String Representation Function -

my_tennis_club/members/models.py:

```py
from django.db import models

class Member(models.Model):
  firstname = models.CharField(max_length=255)
  lastname = models.CharField(max_length=255)
  phone = models.IntegerField(null=True)
  joined_date = models.DateField(null=True)

  def __str__(self):
    return f"{self.firstname} {self.lastname}"
```

127.0.0.1:8000/admin/:

![](https://user-images.githubusercontent.com/32337103/215197241-8c5136e5-80b9-40f9-a814-0bb81ff6c9d2.png)

To Set list_display -

my_tennis_club/members/admin.py:

```py
from django.contrib import admin
from .models import Member

# Register your models here.

class MemberAdmin(admin.ModelAdmin):
  list_display = ("firstname", "lastname", "joined_date",)

admin.site.register(Member, MemberAdmin)
```

127.0.0.1:8000/admin/:

![](https://user-images.githubusercontent.com/32337103/215197817-cc4a6a91-bc57-48fa-aa18-3cd64ab06eba.png)

</details>

+CONDITIONALS AND OPERATORS

<details>
  <summary>25. Template Variables </summary>

templates/template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>Hello {{ firstname }}, how are you?</h1>

    <p>In views.py you can see how to create the variable.</p>
    <p>In template.html you can see how to use the variable.</p>
  </body>
</html>
```

my_tennis_club/members/views.py:

```py
from django.http import HttpResponse
from django.template import loader
from .models import Member

def members(request):
  mymembers = Member.objects.all().values()
  template = loader.get_template('all_members.html')
  context = {
    'mymembers': mymembers,
  }
  return HttpResponse(template.render(context, request))

def details(request, id):
  mymember = Member.objects.get(id=id)
  template = loader.get_template('details.html')
  context = {
    'mymember': mymember,
  }
  return HttpResponse(template.render(context, request))

def main(request):
  template = loader.get_template('main.html')
  return HttpResponse(template.render())

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'firstname': 'Linus',
  }
  return HttpResponse(template.render(context, request))
```

127.0.0.1:8000/testing/:

![012](https://user-images.githubusercontent.com/32337103/215256961-b62a0903-29f3-4aa0-b953-c202138d280f.png)

Create Variables in Template -

templates/template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    {% with firstname="Tobias" %}
    <h1>Hello {{ firstname }}, how are you?</h1>
    {% endwith %}
  </body>
</html>
```

my_tennis_club/members/views:

```py
from django.http import HttpResponse
from django.template import loader
from .models import Member

def members(request):
  mymembers = Member.objects.all().values()
  template = loader.get_template('all_members.html')
  context = {
    'mymembers': mymembers,
  }
  return HttpResponse(template.render(context, request))

def details(request, id):
  mymember = Member.objects.get(id=id)
  template = loader.get_template('details.html')
  context = {
    'mymember': mymember,
  }
  return HttpResponse(template.render(context, request))

def main(request):
  template = loader.get_template('main.html')
  return HttpResponse(template.render())

def testing(request):
  template = loader.get_template('template.html')
  return HttpResponse(template.render())
```

127.0.0.1:8000/testing/:

![](https://user-images.githubusercontent.com/32337103/215258927-9de476d0-5a60-48e3-862b-ec3f12aae73f.png)

Data From a Model -

my_tennis_club/members/views.py:

```py
from django.http import HttpResponse
from django.template import loader
from .models import Member

def members(request):
  mymembers = Member.objects.all().values()
  template = loader.get_template('all_members.html')
  context = {
    'mymembers': mymembers,
  }
  return HttpResponse(template.render(context, request))

def details(request, id):
  mymember = Member.objects.get(id=id)
  template = loader.get_template('details.html')
  context = {
    'mymember': mymember,
  }
  return HttpResponse(template.render(context, request))

def main(request):
  template = loader.get_template('main.html')
  return HttpResponse(template.render())

def testing(request):
  mymembers = Member.objects.all().values()
  template = loader.get_template('template.html')
  context = {
    'mymembers': mymembers,
  }
  return HttpResponse(template.render(context, request))

```

templates/template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <ul>
      {% for x in mymembers %}
      <li>{{ x.firstname }}</li>
      {% endfor %}
    </ul>

    <p>
      In views.py you can see how to import and fetch members from the database.
    </p>
  </body>
</html>
```

127.0.0.1:8000/testing/:

![015](https://user-images.githubusercontent.com/32337103/215259182-e501b4c4-4a57-4cc1-a3f9-ecc1e577591a.png)

</details>

<details>
  <summary>26. Django Conditionals and Operators </summary>

If/Else -

templates/template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    {% if greeting == 1 %}
    <h1>Hello</h1>
    {% else %}
    <h1>Bye</h1>
    {% endif %}

    <p>In views.py you can see what the greeting variable looks like.</p>
  </body>
</html>
```

my_tennis_club/members/views.py:

```py
from django.http import HttpResponse
from django.template import loader
from .models import Member

def members(request):
  mymembers = Member.objects.all().values()
  template = loader.get_template('all_members.html')
  context = {
    'mymembers': mymembers,
  }
  return HttpResponse(template.render(context, request))

def details(request, id):
  mymember = Member.objects.get(id=id)
  template = loader.get_template('details.html')
  context = {
    'mymember': mymember,
  }
  return HttpResponse(template.render(context, request))

def main(request):
  template = loader.get_template('main.html')
  return HttpResponse(template.render())

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'greeting': 1,
  }
  return HttpResponse(template.render(context, request))

```

127.0.0.1:8000/testing/:

![016](https://user-images.githubusercontent.com/32337103/215260865-67cfd700-fb4e-419d-b16c-4f00809c1a9d.png)

If-Elif-Else -

```py
{% if greeting == 1 %}
  <h1>Hello</h1>
{% elif greeting == 2 %}
  <h1>Welcome</h1>
{% else %}
  <h1>Goodbye</h1>
{% endif %}
```

Is equal to -

```py
{% if greeting == 2 %}
  <h1>Hello</h1>
{% endif %}
```

Is not equal to -

```py
{% if greeting != 1 %}
  <h1>Hello</h1>
{% endif %}
```

Is less than -

```py
{% if greeting < 3 %}
  <h1>Hello</h1>
{% endif %}
```

Is less than, or equal to -

```py
{% if greeting <= 3 %}
  <h1>Hello</h1>
{% endif %}
```

Is greater than -

```py
{% if greeting > 1 %}
  <h1>Hello</h1>
{% endif %}
```

Is greater than, or equal to -

```py
{% if greeting >= 1 %}
  <h1>Hello</h1>
{% endif %}
```

And -

```py
{% if greeting == 1 and day == "Friday" %}
  <h1>Hello Weekend!</h1>
{% endif %}
```

Or -

```py
{% if greeting == 1 or greeting == 5 %}
  <h1>Hello</h1>
{% endif %}
```

And/Or -

```py
{% if greeting == 1 and day == "Friday" or greeting == 5 %}
```

In -

```py
{% if 'Banana' in fruits %}
  <h1>Hello</h1>
{% else %}
  <h1>Goodbye</h1>
{% endif %}
```

Not in -

```py
{% if 'Banana' not in fruits %}
  <h1>Hello</h1>
{% else %}
  <h1>Goodbye</h1>
{% endif %}
```

Is -

```py
{% with var1=x var2=x %}
  {% if var1 is var2 %}
    <h1>YES</h1>
  {% else %}
    <h1>NO</h1>
  {% endif %}
{% endwith %}
```

Is not

```py
{% if x is not y %}
  <h1>YES</h1>
{% else %}
  <h1>NO</h1>
{% endif %}
```

</details>

+TEMPLATE TAGS

<details>
  <summary>27. Template Tags - Introduction </summary>

```bs
Tag	            Description

autoescape	    Specifies if autoescape mode is on or off
block	          Specifies a block section
comment	        Specifies a comment section
csrf_token	    Protects forms from Cross Site Request Forgeries
cycle	          Specifies content to use in each cycle of a loop
debug	          Specifies debugging information
extends	        Specifies a parent template
filter	        Filters content before returning it
firstof	        Returns the first not empty variable
for	            Specifies a for loop
if	            Specifies a if statement
ifchanged	      Used in for loops. Outputs a block only if a value has changed since the last iteration
include	        Specifies included content/template
load	          Loads template tags from another library
lorem	          Outputs random text
now	            Outputs the current date/time
regroup	        Sorts an object by a group
resetcycle	    Used in cycles. Resets the cycle
spaceless	      Removes whitespace between HTML tags
templatetag	    Outputs a specified template tag
url	            Returns the absolute URL part of a URL
verbatim	      Specifies contents that should not be rendered by the template engine
widthratio	    Calculates a width value based on the ratio between a given value and a max value
with	          Specifies a variable to use in the block
```

</details>

<details>
  <summary>28. Template Tags - autoescape  </summary>

- The autoescape tag is used to specify if autoescape is on or off.

- If autoescape is on, which is default, HTML code in variables will be escaped.

When escape is on, these characters are escaped:

```bash
< is converted to &lt;
> is converted to &gt;
' is converted to '
" is converted to "
& is converted to &amp;
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    {% autoescape on %}
    <h1>{{ heading }}</h1>
    {% endautoescape %}

    <p>Check out views.py to see what the heading variable looks like.</p>
  </body>
</html>
```

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'heading': 'Hello &lt;i&gt;my&lt;/i&gt; World!',
  }
  return HttpResponse(template.render(context, request))
```

![](https://user-images.githubusercontent.com/32337103/215270069-1a6fb60f-93f1-438f-87c7-96803a0d2723.png)

</details>

<details>
  <summary>29. Template Tags - block </summary>

The block tag has two functions:

- It is a placeholder for content.
- It is content that will replace the placeholder.

In master templates the block tag is a placeholder that will be replaced by a block in a child template with the same name.<br>

In child templates the block tag is content that will replace the placeholder in the master template with the same name.<br>

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('childtemplate.html')
  return HttpResponse(template.render())

```

mymaster.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>Welcome</h1>

    {% block userinfo %}
    <h2>Not registered yet</h2>
    {% endblock %}

    <p>
      Check out the two templates to see what they look like, and views.py to
      see the reference to the child template.
    </p>
  </body>
</html>
```

childtemplate.html:

```bash
{% extends "mymaster.html" %}

{% block userinfo %}
  <h2>John Doe</h2>
  <p>Explorer of life.</p>
{% endblock %}
```

![](https://user-images.githubusercontent.com/32337103/215270392-c5f022ee-5195-4ff0-8fd5-d6050b6cca89.png)

</details>

<details>
  <summary>30. Template Tags - comment </summary>

- The comment tag allows you to add comment sections that will be ignored by Django.

- Comments can be used to make the code more readable.

- Comments can be used to prevent execution when testing code.

- You can add an explanation to your comments to make them more understandable

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  return HttpResponse(template.render())
```

template.html:

```html
<!DOCTYPE html>
<html>
<body>

<h1>Welcome Everyone!</h1>

{% comment "optional heading" %}
  <h1>Greetings!</h2>
{% endcomment %}

</body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215273390-bcc5db2d-d576-4ac0-89a7-f9bf4f767132.png)

</details>

<details>
  <summary>31. Template Tags - csrf_token </summary>

views.py:

```py
from django.http import HttpResponse
from django.views.decorators.csrf import csrf_exempt

@csrf_exempt
def my_view(request):
    return HttpResponse('Hello world')
```

template.html:

```html
<!DOCTYPE html>
<html>
  <head> </head>
  <body>
    <form action="" method="post">
      //csrf token inseted in form {% csrf_token %}
      <h2>registration form</h2>
      <input type="text" />
      <input type="submit" />
    </form>
  </body>
</html>
```

</details>

<details>
  <summary>32. Template Tags - cycle </summary>

- The cycle tag returns different values for different iterations in a loop.

- The first iteration gets the first value, the second iteration gets the second value etc.

- You can have as many values as you like.

- If there are more iterations that values, the cycle resets and starts at value 1

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'fruits': ['Apple', 'Banana', 'Cherry', 'Orange']
    }
  return HttpResponse(template.render(context, request))
```

template.html:

```html
<!DOCTYPE html>
<html>
<body>

<ul>
{% for x in fruits %}
  <li style='color:{% cycle 'red' 'green' 'blue' 'pink' %}'>
    {{ x }}
  </li>
{% endfor %}
</ul>

<p>Check out views.py to see what the fruits variable looks like.</p>

</body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215275833-f39e7516-ba59-43e4-ac65-57e5fc447996.png)

</details>

<details>
  <summary>33. Template Tags - debug	</summary>

Outputs a whole load of debugging information, including the current context and imported modules. {% debug %} outputs nothing when the DEBUG setting is False.

</details>

<details>
  <summary>34. Template Tags - extends </summary>

- The extends tag is used to specify that this template needs a parent template.

- The extends tag takes one argument, which is the name of the parent template.

- When a child template with a parent template is requested, Django uses the parent template as a "skeleton" and fills it with content from the child template, according to the matching block tags.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('childtemplate.html')
  return HttpResponse(template.render())

```

mymaster.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>Welcome</h1>
    <hr />

    {% block heading %}
    <h2>No name</h2>
    {% endblock %}

    <h2>My Cars</h2>

    <ul>
      {% block cars %}
      <li>No cars</li>
      {% endblock %}
    </ul>

    <p>
      Check out the two templates to see what they look like, and views.py to
      see the reference to the child template.
    </p>
  </body>
</html>
```

childtemplate.html:

```bash
{% extends "mymaster.html" %}

{% block heading %}
  <h2>John Doe</h2>
  <p>Explorer of life</p>
{% endblock %}

{% block cars %}
  <li>Ford</li>
  <li>Volvo</li>
  <li>Audi</li>
{% endblock %}
```

![](https://user-images.githubusercontent.com/32337103/215276184-abf815c2-10dc-461f-ae52-6aa96afe3b50.png)

</details>

<details>
  <summary>35. Template Tags - filter </summary>

- The filter tag allows you to run a section of code through a filter, and return it according to the filter keyword(s).

- To add multiple filters, separate the keywords with the pipe | character.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  return HttpResponse(template.render())

```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>Welcome Everyone!</h1>

    {% filter upper %}
    <p>Have a great day!</p>
    {% endfilter %}
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215276359-39aaf01c-6492-453b-a20e-64f9ec2a70db.png)

</details>

<details>
  <summary>36. Template Tags - firstof	 </summary>

- The firstof tag returns the first argument that is not an empty variable.

- Empty variables can be an empty string "", or a zero number 0, or a boolean false.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'x': 'Volvo',
    'y': 'Ford',
    'z': 'BMW',
    }
  return HttpResponse(template.render(context, request))
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>{% firstof x y z %}</h1>

    <p>Check out views.py to see the content of the x, y, and z variables.</p>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215277341-9b630872-fa24-4ad8-bab4-ffe82362e06f.png)

</details>

<details>
  <summary>37. Template Tags - for </summary>

- The for tag allows you to iterate over items in an object.

- Objects can be array-like objects like a Python list or object-like objects like a Python dictionary.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'fruits': ['Apple', 'Banana', 'Cherry', 'Orange']
    }
  return HttpResponse(template.render(context, request))
```

template.html:

```HTML
<!DOCTYPE html>
<html>
<body>

<ul>
  {% for x in fruits %}
    <li>{{ x }}</li>
  {% endfor %}
</ul>

<p>Check out views.py to see what the fruits variable looks like.</p>

</body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215285954-9eee4f77-0eb0-4eae-90d7-c3a89dfc99c4.png)

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'mycar': {
      'brand': 'Ford',
      'model': 'Mustang',
      'year': '1964',
      }
    }
  return HttpResponse(template.render(context, request))

```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    {% for x, y in mycar.items %}
    <p>The {{ x }} is {{ y }}.</p>
    {% endfor %}

    <p>Check out views.py to see what the mycar dictionary looks like.</p>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215286111-dd9fe999-9eaf-4667-ada9-f49294e3f210.png)

</details>

<details>
  <summary>37a. Template Tags - forloop.counter </summary>

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'fruits': ['Apple', 'Banana', 'Cherry', 'Orange']
    }
  return HttpResponse(template.render(context, request))
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <ul>
      {% for x in fruits %}
      <li>{{ forloop.counter }}</li>
      {% endfor %}
    </ul>

    <p>Check out views.py to see what the fruits object look like.</p>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215287416-5d42c636-5d6f-4640-b8a8-30f4f6ea4dae.png)

</details>

<details>
  <summary>37b. Template Tags - forloop.counter0 </summary>

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'fruits': ['Apple', 'Banana', 'Cherry', 'Orange']
    }
  return HttpResponse(template.render(context, request))
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <ul>
      {% for x in fruits %}
      <li>{{ forloop.counter0 }}</li>
      {% endfor %}
    </ul>

    <p>Check out views.py to see what the fruits object look like.</p>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215287625-7515c4e2-0452-4e9a-af28-eb88d5c53938.png)

</details>

<details>
  <summary>37c. Template Tags - forloop.first </summary>

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'fruits': ['Apple', 'Banana', 'Cherry', 'Orange']
    }
  return HttpResponse(template.render(context, request))
```

template.html:

```py
<!DOCTYPE html>
<html>
<body>

<ul>
  {% for x in fruits %}
    <li
    {% if forloop.first %}
      style='background-color:lightblue;'
    {% endif %}
    >{{ x }}</li>
  {% endfor %}
</ul>

<p>Check out views.py to see what the fruits object look like.</p>

</body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215287969-9f101f82-519c-4fed-987f-90d65d3165ca.png)

</details>

<details>
  <summary>37d. Template Tags - forloop.last </summary>

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'fruits': ['Apple', 'Banana', 'Cherry', 'Orange']
    }
  return HttpResponse(template.render(context, request))
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <ul>
      {% for x in fruits %}
      <li {% if forloop.last %} style="background-color:lightblue;" {% endif %}>
        {{ x }}
      </li>
      {% endfor %}
    </ul>

    <p>Check out views.py to see what the fruits object look like.</p>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215288123-0a77085f-9afb-4ddd-83ab-c5556cc8c3d8.png)

</details>

<details>
  <summary>37e. Template Tags - forloop.parentloop </summary>

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'cars': ['Ford', 'Volvo', 'BMW'],
    'colors': ['Red', 'Green', 'Blue']
    }
  return HttpResponse(template.render(context, request))
```

template.html:

```py
<!DOCTYPE html>
<html>
<body>

<ul>
  {% for x in cars %}
    <li>{{ x }}:
      <ul>
        {% for y in colors %}
          <li>
            {{ forloop.parentloop.counter }}
            {{ y }}
          </li>
        {% endfor %}
      </ul>
    </li>
  {% endfor %}
</ul>

<p>Check out views.py to see what the cars and colors object look like.</p>

</body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215288312-62fababe-ecec-4fc2-b54f-463752e525c4.png)

</details>

<details>
  <summary>37f. Template Tags - forloop.revcounter </summary>

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'fruits': ['Apple', 'Banana', 'Cherry', 'Orange']
    }
  return HttpResponse(template.render(context, request))

```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <ul>
      {% for x in fruits %}
      <li>{{ forloop.revcounter }}</li>
      {% endfor %}
    </ul>

    <p>Check out views.py to see what the fruits object look like.</p>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215288555-6dd476a2-0c7a-423b-9bcf-b4949c288134.png)

</details>

<details>
  <summary>37g. Template Tags - forloop.revcounter0 </summary>

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'fruits': ['Apple', 'Banana', 'Cherry', 'Orange']
    }
  return HttpResponse(template.render(context, request))
```

template.html:

```py
<!DOCTYPE html>
<html>
<body>

<ul>
  {% for x in fruits %}
    <li>{{ forloop.revcounter }}</li>
  {% endfor %}
</ul>

<p>Check out views.py to see what the fruits object look like.</p>

</body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215288704-6c62f5ad-9c1c-4b6e-85a2-4db3cfe4bf4b.png)

</details>

<details>
  <summary>38. Template Tags - if </summary>

- The if tag allows you to write conditional statements.

- Use if statements to output a block of code if a condition is true.

- You can use else or elif (short for "else if") to specify what to do when the if condition is false.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'myvar': 1
    }
  return HttpResponse(template.render(context, request))

```

template.html:

```py
<!DOCTYPE html>
<html>
<body>

{% if myvar == 1 %}
  <h1>Hello!</h1>
{% endif %}

<p>Check out views.py to see what the myvar variable looks like.</p>

</body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215289374-01ae974d-64c2-4fb9-865c-5567c4b70454.png)

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'myvar': 2
  }
  return HttpResponse(template.render(context, request))
```

template.html:

```py
<!DOCTYPE html>
<html>
<body>

{% if myvar == 1 %}
  <h1>Hello!</h1>
{% elif myvar == 2 %}
  <h1>Welcome!</h1>
{% else %}
  <h1>Greetings!</h1>
{% endif %}

<p>Check out views.py to see what the myvar variable looks like.</p>

</body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215290382-596fa475-3e4f-4a51-8ec6-dc2795e7d337.png)

</details>

<details>
  <summary>39. Template Tags - ifchanged </summary>

- The ifchanged tag allows you to check a value in a loop and output a code if the value has changed since the last iteration.

- If the iteration object has many values per iteration, you can specify which value to check, and the block of code will only displayed if that value has changed since the last iteration.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'mylist': [1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 3, 4, 5]
    }
  return HttpResponse(template.render(context, request))
```

template.html:

```bash
<!DOCTYPE html>
<html>
<body>

<ul>
  {% for x in mylist %}
    {% ifchanged %}
      <li>{{ x }}</li>
    {% endifchanged %}
  {% endfor %}
</ul>

<p>Check out views.py to see what the mylist object look like.</p>

</body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215290542-2a80c3b1-625f-4077-b188-6cb41563102c.png)

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'cars': [
      {
        'brand': 'Ford',
        'model': 'Mustang',
        'year': '1964',
      },
      {
        'brand': 'Ford',
        'model': 'Bronco',
        'year': '1970',
      },
      {
        'brand': 'Ford',
        'model': 'Sierra',
        'year': '1981',
      },
      {
        'brand': 'Volvo',
        'model': 'XC90',
        'year': '2016',
      },
      {
        'brand': 'Volvo',
        'model': 'P1800',
        'year': '1964',
      }]
    }
  return HttpResponse(template.render(context, request))
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    {% for x in cars %} {% ifchanged x.brand %}
    <h1>{{ x.brand }}:</h1>
    {% endifchanged %}
    <p>{{ x.model }}, {{ x.year }}</p>
    {% endfor %}

    <p>Check out views.py to see what the cars object look like.</p>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215290655-dedf12cf-f8af-4c09-bc34-53a7b0e9aed4.png)

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'mylist': [1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 3, 4, 5]
    }
  return HttpResponse(template.render(context, request))
```

template.html:

```py
<!DOCTYPE html>
<html>
<body>

{% for x in mylist %}
  {% ifchanged %}
    <p>New value: {{ x }}</p>
  {% else %}
    <p>Same value: {{ x }}</p>
  {% endifchanged %}
{% endfor %}

<p>Check out views.py to see what cars object look like.</p>

</body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215291268-3f5646a2-5cf9-4825-8dd3-78ddd1694353.png)

</details>

<details>
  <summary>40. Template Tags - include </summary>

- The include tag allows you to include content from another template.

- Place the include tag exactly where you want the content to be displayed.

- This is useful when you have the same content for many pages.

- You can also send variables into the template, by using the with keyword.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  return HttpResponse(template.render())
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    {% include "mymenu.html" with me="ALEXANDER" sponsor="W3SCHOOLS" %}

    <h1>Welcome</h1>

    <p>This is my web site.</p>

    <p>Check out mymenu.html to see the HTML content of the include.</p>
  </body>
</html>
```

mymenu.html:

```html
<div>HOME | {{ me }} | ABOUT | FORUM | {{ sponsor }}</div>
```

![](https://user-images.githubusercontent.com/32337103/215291493-d86a684c-a81c-44b6-948f-8c10b52415c4.png)

</details>

<details>
  <summary>41. Template Tags - load </summary>

Loads template tags from another library.

```py

```

</details>

<details>
  <summary>42. Template Tags - lorem  </summary>

- The lorem tag inserts a specified amount of random text.

- The "random" text is the famous "Lorum ipsum" text, in lower case letters.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  return HttpResponse(template.render())
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    {% lorem 50 w %}
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215291751-4f1e3f19-4c58-4647-bf8a-2f164dbf26f5.png)

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    {% lorem 5 p %}
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215291835-de7e51f7-a543-4a4d-b646-4a20f56d8b76.png)

```py
{% lorem count method random %}
```

</details>

<details>
  <summary>43. Template Tags - now </summary>

The now tag inserts the current date and/or time, according to the specified format.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  return HttpResponse(template.render())
```

template.html:

```py
<!DOCTYPE html>
<html>
<body>

<h1>{% now "Y-m-d G:i:s" %}</h1>

</body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215291958-ecc2a2d3-2960-4c12-ad6c-f99b0f18ab3b.png)

```py
{% now format %}
```

</details>

<details>
  <summary>44. Template Tags - regroup </summary>

- The regroup tag returns a new object grouped by a specified value.

- The result is divided into one GroupedResult object for each group, making the newlist object.

- Make sure the object is sorted correctly before regrouping, otherwise you will end up with groups with the same grouper name.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'cars': [
      {
        'brand': 'Ford',
        'model': 'Mustang',
        'year': '1964',
      },
      {
        'brand': 'Ford',
        'model': 'Bronco',
        'year': '1970',
      },
      {
        'brand': 'Ford',
        'model': 'Sierra',
        'year': '1981',
      },
      {
        'brand': 'Volvo',
        'model': 'XC90',
        'year': '2016',
      },
      {
        'brand': 'Volvo',
        'model': 'P1800',
        'year': '1964',
      }]
    }
  return HttpResponse(template.render(context, request))
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    {% regroup cars by brand as newlist %} {{ newlist }} {% for x in newlist %}
    <h1>{{ x.grouper }}</h1>
    {% for y in x.list %}
    <p>{{ y.model }}: {{ y.year }}</p>
    {% endfor %} {% endfor %}

    <p>Check out views.py to see what the cars list looks like.</p>
  </body>
</html>
```

The result from {% regroup cars by brand as newlist %}:

```py
[
  GroupedResult(
    grouper='Ford',
    list=[
      {
        'brand': 'Ford',
        'model': 'Mustang',
        'year': '1964'
      },
      {
        'brand': 'Ford',
        'model': 'Bronco',
        'year': '1970'
      },
      {
        'brand': 'Ford',
        'model': 'Sierra',
        'year': '1981'
      }
    ]
  ),
  GroupedResult(
    grouper='Volvo',
    list=[
      {
        'brand': 'Volvo',
        'model': 'XC90',
        'year': '2016'
      },
      {
        'brand': 'Volvo',
        'model': 'P1800',
        'year': '1964'
      }
    ]
  )
]
```

![](https://user-images.githubusercontent.com/32337103/215292099-a778f455-c480-45ed-b391-3d942d0e4fc5.png)

```py
{% regroup object by object.property as newname %}
```

</details>

<details>
  <summary>45. Template Tags - resetcycle </summary>

- The resetcycle tag is used inside a cycle, and resets the cycle, making it start at the beginning.

- It does not reset the loop, only the cycle.

- If you have multiple cycles, you can specify which one to reset with the name argument.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'fruits': ['Apple', 'Banana', 'Cherry', 'Orange']
    }
  return HttpResponse(template.render(context, request))
```

template.html:

```html
<!DOCTYPE html>
<html>
<body>

<ul>
  {% for x in fruits %}
    <li style='color:{% cycle 'red' 'green' 'blue' 'pink' %}'>
      {{ x }}
    </li>
    {% if x == "Banana" %}
      {% resetcycle %}
    {% endif %}
  {% endfor %}
</ul>

<p>Check out views.py to see what the fruits variable looks like.</p>

</body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215292269-bde32742-f152-46f3-ac8c-b2a8422e54ad.png)

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'fruits': ['Apple', 'Banana', 'Cherry', 'Orange']
    }
  return HttpResponse(template.render(context, request))
```

template.html:

```html
<!DOCTYPE html>
<html>
<body>

<ul>
{% for x in fruits %}
  <li style='
      color:{% cycle 'red' 'green' 'blue' 'pink' as mycolor %};
      background:{% cycle 'grey' 'beige' 'red' 'purple' as mybg %};
    '>
    {{ x }}
  </li>
  {% if x == "Banana" %}
    {% resetcycle mybg %}
  {% endif %}
{% endfor %}
</ul>

<p>Check out views.py to see what the fruits variable looks like.</p>

</body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215292325-82fc7cab-dbc2-445b-a96b-d974a790f3ea.png)

</details>

<details>
  <summary>46. Template Tags - spaceless </summary>

- The spaceless tag is used to remove any space between tags, in the code.

- The spaceless tag removes any whitespaces, new lines and tabs.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'fruits': ['Apple', 'Banana', 'Cherry', 'Orange']
    }
  return HttpResponse(template.render(context, request))
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    {% spaceless %}
    <ul>
      {% for x in fruits %}
      <li>{{ x }}</li>
      {% endfor %}
    </ul>
    {% endspaceless %}

    <p>
      Right-click the result and view the page source. The entire HTML code is
      written in one line.
    </p>

    <p>Check out views.py to see what the fruits variable looks like.</p>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215292391-dbc43074-3a56-48d3-996b-a9941b0b358e.png)

</details>

<details>
  <summary>47. Template Tags - templatetag </summary>

- The templatetag tag is used to display characters that are normally used to perform Django tasks.

- Each tag character, like {{, {% and {#, has their own name.

```bash
Name	          Output
openvariable	  {{
closevariable	  }}
openblock	      {%
closeblock	    %}
openbrace	      {
closebrace	    }
opencomment	    {#
closecomment	  #}
```

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  return HttpResponse(template.render())
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>{% templatetag openblock %} extends {% templatetag closeblock %}</h1>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215292512-f1b80172-ca7b-4e80-89d6-1955784d8e12.png)

</details>

<details>
  <summary>48. Template Tags - url </summary>

Returns the absolute URL part of a URL.

```py
{% url login.views.login_view %}
```

</details>

<details>
  <summary>49. Template Tags - verbatim </summary>

- The verbatim tag is used to stop Django from executing code.

- Anything between {% verbatim %} and {% endverbatim %} will not be executed, but rendered as output instead.

- To be sure that you refer to the correct verbatim code block, you can add a name to it:

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'fruits': ['Apple', 'Banana', 'Cherry', 'Orange']
    }
  return HttpResponse(template.render(context, request))
```

template.html:

```py
<!DOCTYPE html>
<html>
<body>

{% verbatim %}
  {% for x in fruits %}
    <h1>{{ x }}</h1>
  {% endfor %}
{% endverbatim %}

</body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215292811-2cf341ef-6139-4edc-b808-ec89c7cb2966.png)

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    {% verbatim mycode %} {% for x in fruits %} {% verbatim %}
    <h1>{{ x }}</h1>
    {% endverbatim %} {% endfor %} {% endverbatim mycode %}
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215292853-5ce3a378-5453-4145-80fe-9f41f63bda0c.png)

</details>

<details>
  <summary>50. Template Tags - widthratio </summary>

Calculates a width value based on the ratio between a given value and a max value.

```py

```

</details>

<details>
  <summary>A51. Template Tags - with  </summary>

- The with tag is used to create variables in Django templates.

- This can be useful when you need to ask for the same variable many times, like in a loop.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  return HttpResponse(template.render())
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    {% with firstname="Stalikken" %}
    <h1>Hello {{ firstname }}</h1>
    {% endwith %}
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215292934-de95c829-2e36-4af1-8844-a5f539e8849a.png)

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'fruits': ['Apple', 'Banana', 'Cherry', 'Orange']
    }
  return HttpResponse(template.render(context, request))
```

template.html:

```code
<!DOCTYPE html>
<html>
<body>

{% with myvar=fruits|length %}
  {% for x in fruits %}
     <p>{{ x }} is one of {{ myvar }} fruits.</p>
  {% endfor %}
{% endwith %}

<p>Check out views.py to see what the fruits list looks like.</p>

</body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215292976-99312dc9-935f-4ac7-ba58-4ff299544421.png)

</details>

<details>
  <summary>52. Template Tags - Reversed keyword </summary>

The reversed keyword is used when you want to do the loop in reversed order.

views.py:

```py
from django.http import HttpResponse, HttpResponseRedirect
from django.template import loader
from .models import Member

def testing(request):
  mymembers = Member.objects.all().values()
  template = loader.get_template('template.html')
  context = {
    'members': mymembers,
  }
  return HttpResponse(template.render(context, request))

```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    {% for x in members reversed %}
    <h1>{{ x.id }}</h1>
    <p>{{ x.firstname }} {{ x.lastname }}</p>
    {% endfor %}

    <p>
      In views.py you can see how to import and fetch members from the database.
    </p>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215293203-bd6a067c-660a-479d-8cad-72e8b12a9cb7.png)

</details>

<details>
  <summary>53. Template Tags - Empty keyword </summary>

- The empty keyword can be used if you want to do something special if the object is empty.

- The empty keyword can also be used if the object does not exist.

views.py:

```py
from django.http import HttpResponse, HttpResponseRedirect
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'emptytestobject': [],
  }
  return HttpResponse(template.render(context, request))
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <ul>
      {% for x in emptytestobject %}
      <li>{{ x.firstname }}</li>
      {% empty %}
      <li>No members</li>
      {% endfor %}
    </ul>

    <p>In views.py you can see the emptytestobject.</p>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215293477-65d7ce47-d730-4328-9b1f-24235855825a.png)

views.py:

```py
from django.http import HttpResponse, HttpResponseRedirect
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'fruits': ['Apple', 'Banana', 'Cherry'],
  }
  return HttpResponse(template.render(context, request))

```

template.html:

```py
<!DOCTYPE html>
<html>
<body>

<ul>
  {% for x in myobject %}
    <li>{{ x.firstname }}</li>
  {% empty %}
    <li>No members</li>
  {% endfor %}
</ul>

<p>In views.py you can see that there is no myobject variable.</p>

</body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215293538-b2cdcb56-df37-4cb3-ac6e-b778cc7490b4.png)

</details>

<details>
  <summary>54. Template Tags - Comments </summary>

- Comments allows you to have sections of code that should be ignored.

- You can add a message to your comment, to help you remember why you wrote the comment, or as message to other people reading the code.

- You can also use the {# ... #} tags when commenting out code, which can be easier for smaller comments.

- Views are written in Python, and Python comments are written with the # character.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  return HttpResponse(template.render())
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>Welcome Everyone</h1>
    {% comment %}
    <h1>Welcome ladies and gentlemen</h1>
    {% endcomment %}
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215293655-e05a591b-333f-43b4-9178-e78940ec2048.png)

```html
<h1>Welcome Everyone</h1>
{% comment "this was the original welcome message" %}
<h1>Welcome ladies and gentlemen</h1>
{% endcomment %}
```

```html
<h1>Welcome{# Everyone#}</h1>
```

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  #context = {
  # 'var1': 'John',
  #}
  return HttpResponse(template.render())
```

</details>

<details>
  <summary>55. Template Tags - Include </summary>

- The include tag allows you to include a template inside the current template.

- This is useful when you have a block of content that is the same for many pages.

- You can send variables into the template by using the with keyword.

- In the include file, you refer to the variables by using the {{ variablename }} syntax.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  return HttpResponse(template.render())
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>Hello</h1>

    <p>This page contains a footer in a template.</p>

    {% include 'footer.html' %}

    <p>
      Check out the two templates to see what they look like, and views.py to
      see the reference to the child template.
    </p>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215293916-0331fa94-ed0e-4c9d-a137-7afbb16594c5.png)

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  return HttpResponse(template.render())

```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    {% include "mymenu.html" with me="TOBIAS" sponsor="W3SCHOOLS" %}

    <h1>Welcome</h1>

    <p>This is my web site.</p>

    <p>Check out mymenu.html to see the HTML content of the include.</p>
  </body>
</html>
```

mymenu.html:

```py
<div>HOME | {{ me }} | ABOUT | FORUM | {{ sponsor }}</div>
```

![](https://user-images.githubusercontent.com/32337103/215293994-22060211-83c7-41ce-bd51-4adf2372bf0c.png)

</details>

+FILTER REFERENCE

<details>
  <summary>56. Filter Reference - add </summary>

- The add filter adds a specified argument to a value.

- The add filter tries to convert the values into numbers and return the sum, but if is not possible to convert the values into numbers, the specified argument will be added at the end.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'prices': [70, 35, 52],
  }
  return HttpResponse(template.render(context, request))
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    {% for x in prices %}
    <h1>The price is {{ x|add:"10" }} dollars.</h1>
    {% endfor %}

    <p>In views.py you can see what the prices variable looks like.</p>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215329917-31ca505c-7882-4b94-b4db-4b97fc307bf8.png)

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'fruits': ['Apple', 'Banana', 'Cherry'],
  }
  return HttpResponse(template.render(context, request))
```

template.html:

```py
<!DOCTYPE html>
<html>
<body>

{% for x in fruits %}
  <h1>{{ x|add:"-CHECK" }}</h1>
{% endfor %}

<p>In views.py you can see what the fruits variable looks like.</p>

</body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215330058-4f1f81ab-b653-4bf2-b5e6-25fc066c2296.png)

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'fruits': ['Apple', 'Banana', 'Cherry'],
    'vegetables': ['Asparagus', 'Broccoli', 'Carrot'],
  }
  return HttpResponse(template.render(context, request))
```

template.html:

```py
<!DOCTYPE html>
<html>
<body>

{{ fruits|add:vegetables }}

<p>In views.py you can see what the fruits
and vegetables variables look like.</p>

</body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215330188-5b8131da-d03a-40a3-bccb-c19d54edda37.png)

</details>

<details>
  <summary>57. Filter Reference - addslashes </summary>

- The addslashes filter adds a slash \ character before any quotes.

- This can be helpful when you are dealing with JavaScript, and you have to escape quote characters.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'name': "Capt'n Jack",
  }
  return HttpResponse(template.render(context, request))
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>{{ name|addslashes }}</h1>

    <p>In views.py you can see what the name variable looks like.</p>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215330828-5a372836-3cdb-41b7-a280-3e048161404f.png)

</details>

<details>
  <summary>58. Filter Reference - capfirst </summary>

The capfirst filter capitalizes the first letter of the value.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'animal': 'lion',
  }
  return HttpResponse(template.render(context, request))
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>{{ animal|capfirst }}</h1>

    <p>In views.py you can see what the animal variable looks like.</p>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215331045-40a87606-e020-4e1e-ba55-c61d4a65840e.png)

</details>

<details>
  <summary>59. Filter Reference - center </summary>

The center filter places the value in the center of a value of the specified length.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'name': 'Tobias',
  }
  return HttpResponse(template.render(context, request))
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>{{ name|center:20 }}</h1>

    <p>
      In HTML the display does not show more than one space, but if you view the
      page source you will see that there are 20 characters between &lt;h1&gt;
      and &lt;/h1&gt;.
    </p>

    <p>
      Or, to demonstrate we can use a textarea to see that "Tobias" is center
      aligned:
    </p>

    <textarea>{{ name|center:20 }}</textarea>

    <p>In views.py you can see what the name variable looks like.</p>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215331340-2a3a1963-0686-44bd-bb14-10a215a3982d.png)

</details>

<details>
  <summary>60. Filter Reference - cut </summary>

- The cut filter removes the specified phrase from the value.

- The cut filter is case sensitive.

- All occurences of the specified phrase/character are removed.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'name': 'Emil Refsnes',
  }
  return HttpResponse(template.render(context, request))
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>{{ name|cut:"snes" }}</h1>

    <p>In views.py you can see what the name variable looks like.</p>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215331712-6c51ca13-a1aa-4290-a16f-b006dc2dc5b0.png)

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'name': 'Emil Refsnes',
  }
  return HttpResponse(template.render(context, request))
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>{{ name|cut:"e" }}</h1>

    <p>In views.py you can see what the name variable looks like.</p>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215331793-64c3a751-c631-4463-bf48-4a6c822afc57.png)

</details>

<details>
  <summary>61. Filter Reference - default </summary>

- The default filter allows you to specify a default value to use if the value evaluates to False.

Values that evaluates to False are:

- Empty Strings ""
- Any numeric 0
- Any empty object [], (), {}, set(), range(0)
- None
- False

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'colors': ['Red', 'Green', 'Blue', '', 'Yellow']
  }
  return HttpResponse(template.render(context, request))
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    {% for x in colors %}
    <h1>{{ x|default:"nocolor" }}</h1>
    {% endfor %}

    <p>In views.py you can see what the colors variable looks like.</p>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215332377-323885df-93f8-45b8-bf0f-e06a828a575b.png)

</details>

<details>
  <summary>62. Filter Reference - default if none </summary>

- The default_if_none filter allows you to specify a default value to use if the value is None.

- The value has to be exactly None for this filter to have effect.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'colors': ['Red', None, 'Blue', '', 'Yellow']
  }
  return HttpResponse(template.render(context, request))
```

template.html:

```py
<!DOCTYPE html>
<html>
<body>

{% for x in colors %}
  <h1>{{ x|default_if_none:"nocolor" }}</h1>
{% endfor %}

<p>In views.py you can see what the colors variable looks like.</p>

</body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215332945-19576437-2c74-4c2d-9b39-774d585609f1.png)

</details>

<details>
  <summary>63. Filter Reference - dictsort </summary>

- The dictsort filter sorts a dictionary by the specified field.

- The dictsort filter sorts ascending.

- Use the dictsortreversed filter to sort descending.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'cars': [
      {'brand': 'Ford', 'model': 'Mustang', 'year': 1964},
      {'brand': 'Volvo', 'model': 'XC90', 'year': 2022},
      {'brand': 'Volvo', 'model': 'P1800', 'year': 1962},
      {'brand': 'Ford', 'model': 'Focus', 'year': 2004},
    ]
  }
  return HttpResponse(template.render(context, request))
```

template.html:

```py
<!DOCTYPE html>
<html>
<body>

{% for x in cars|dictsort:"year" %}
  <p>{{ x.year }} {{ x.brand }} {{ x.model }}.</p>
{% endfor %}

<p>In views.py you can see what the colors variable looks like.</p>

</body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215333363-4679cb6d-0fe7-454e-ac27-423d13e0d974.png)

</details>

<details>
  <summary>64. Filter Reference - dictsortreversed </summary>

- The dictsortreversed filter sorts a dictionary by the specified field, descending.

- Use the dictsort filter to sort ascending.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'cars': [
      {'brand': 'Ford', 'model': 'Mustang', 'year': 1964},
      {'brand': 'Volvo', 'model': 'XC90', 'year': 2022},
      {'brand': 'Volvo', 'model': 'P1800', 'year': 1962},
      {'brand': 'Ford', 'model': 'Focus', 'year': 2004},
    ]
  }
  return HttpResponse(template.render(context, request))
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    {% for x in cars|dictsortreversed:"year" %}
    <p>{{ x.year }} {{ x.brand }} {{ x.model }}.</p>
    {% endfor %}

    <p>In views.py you can see what the colors variable looks like.</p>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215334222-18ee4b35-c15a-4796-b938-1cc8c6f0a2fe.png)

</details>

<details>
  <summary>65. Filter Reference - divisibleby </summary>

The divisibleby filter returns True if the value is divisible by the argument, otherwise it returns False.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'totalsum': 40,
  }
  return HttpResponse(template.render(context, request))
```

template.html:

```py
<!DOCTYPE html>
<html>
<body>

{% if totalsum|divisibleby:5 %}
  <h1>Yes, it is!</h1>
{% endif %}

<p>In views.py you can see what the totalsum variable looks like.</p>

</body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215334771-4988bd47-1514-46d1-9bfd-afc6c367a7b4.png)

</details>

<details>
  <summary>66. Filter Reference - escape </summary>

The escape filter escapes HTML characters from the value.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'heading': 'Hello &lt;i>my&lt;/i> World!',
  }
  return HttpResponse(template.render(context, request))
```

```html
<!DOCTYPE html>
<html>
  <body>
    {% autoescape off %}
    <h1>{{ heading|escape }}</h1>
    <h1>{{ heading }}</h1>
    {% endautoescape %}

    <p>In views.py you can see what the heading variable looks like.</p>

    <p>
      <strong>Note:</strong>
      Escaping HTML characters is a default setting in Django, so we have to
      turn off autoescape in the example to see the difference.
    </p>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215335205-da51b744-0cb1-4f7a-a4aa-d8c10caa0f12.png)

</details>

<details>
  <summary>67. Filter Reference - escapejs </summary>

The escapejs filter escapes text to be used in JavaScript strings.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'var1': 'John\nDoe',
  }
  return HttpResponse(template.render(context, request))
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <h3>Without escapejs:</h3>
    <button onclick="alert('{{ var1 }}')">Click me</button>

    <h3>With escapejs:</h3>
    <button onclick="alert('{{ var1|escapejs }}')">Click me</button>

    <p>
      Try clicking both buttons. The JavaScript without the escapejs filter will
      raise an error.
    </p>

    <p>In views.py you can see what the var1 variable looks like.</p>
  </body>
</html>
```

</details>

<details>
  <summary>68. Filter Reference - filesizeformat </summary>

- The filesizeformat filter converts a large number into a more human readable format.

Examples:

- 1024 is converted into 1.0 KB.

- 524288 is converted into 512.0 KB.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'size': 26214400
  }
  return HttpResponse(template.render(context, request))
```

template.html:

```py
<!DOCTYPE html>
<html>
<body>

<h1>{{ size|filesizeformat }}</h1>

<p>In views.py you can see what the size variable looks like.</p>

</body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215335665-dd213300-acd1-478a-9f40-e6dbbc671eb1.png)

</details>

<details>
  <summary>69. Filter Reference - first </summary>

- The first filter returns the first item of an object.

- For strings, the first filter returns the first character.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'fruits': ['Apple', 'Banana', 'Cherry', 'Orange']
    }
  return HttpResponse(template.render(context, request))
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>{{ fruits|first }}</h1>

    <p>In views.py you can see what the fruits variable looks like.</p>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215335849-f19ea176-b87b-4704-a7e4-27625e012486.png)

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'firstname': 'Emil',
    'lastname': 'Refsnes',
  }
  return HttpResponse(template.render(context, request))
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>{{ firstname|first }}</h1>

    <p>In views.py you can see what the firstname variable looks like.</p>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215335911-fba4513b-0462-4bae-9aaf-5e95d55eb919.png)

</details>

<details>
  <summary>70. Filter Reference - floatformat </summary>

- The floatformat filter rounds a floating-point number to the specified number of decimals, or one, if no decimal argument is specified.

- If the argument value is a positive number, the value will be displayed with the specified number of decimals, even if the value is an integer.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'mynumber': 7.122489,
  }
  return HttpResponse(template.render(context, request))
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>{{ mynumber|floatformat:2 }}</h1>

    <p>In views.py you can see what the mynumber variable looks like.</p>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215336012-5bc68756-d58b-4482-a4c9-8b0bb885c039.png)

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  return HttpResponse(template.render())
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <p>{{ 7.122489|floatformat:2 }}</p>
    <p>{{ 7.1|floatformat:2 }}</p>
    <p>{{ 7|floatformat:2 }}</p>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215336096-8601e42d-31d6-42b8-9ff7-e48bc6ee1856.png)

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  return HttpResponse(template.render())
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <p>{{ 7.122489|floatformat:-2 }}</p>
    <p>{{ 7.1|floatformat:-2 }}</p>
    <p>{{ 7|floatformat:-2 }}</p>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215336338-8c072038-44e3-4281-8815-be0c85a72122.png)

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  return HttpResponse(template.render())
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <p>{{ 7.122489|floatformat:-2 }}</p>
    <p>{{ 7.1|floatformat:-2 }}</p>
    <p>{{ 7|floatformat:-2 }}</p>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215336425-a1d7acf2-d1fe-4dd5-bd42-dc9061b68f43.png)

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'mynumber': 981358286,
  }
  return HttpResponse(template.render(context, request))
```

template.html:

```py
<!DOCTYPE html>
<html>
<body>

<h1>{{ mynumber|floatformat:"2g" }}</h1>

<p>In views.py you can see what the mynumber variable looks like.</p>

</body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215336543-ade9c2e7-9caf-4215-8e86-3ddb5d32684d.png)

</details>

<details>
  <summary>71. Filter Reference - get_digit </summary>

The get_digit filter returns the specified digit from a number, counting from the end of the number.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'mynumber': 75641,
  }
  return HttpResponse(template.render(context, request))
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>{{ mynumber|get_digit:2 }}</h1>

    <p>In views.py you can see what the mynumber variable looks like.</p>
  </body>
</html>
```

![](https://user-images.githubusercontent.com/32337103/215336894-da367535-4fe5-41dc-986f-098f5ec4400f.png)

</details>

<details>
  <summary>72. Filter Reference - join </summary>

- The join filter takes all items in an iterable and joins them into one string.

- A string must be specified as the separator.

views.py:

```py
from django.http import HttpResponse
from django.template import loader

def testing(request):
  template = loader.get_template('template.html')
  context = {
    'fruits': ['Apple', 'Banana', 'Cherry', 'Orange']
    }
  return HttpResponse(template.render(context, request))
```

template.html:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>{{ fruits|join:"#" }}</h1>

    <p>In views.py you can see what the fruits variable looks like.</p>
  </body>
</html>
```

</details>

<details>
  <summary>73. Filter Reference - join_script </summary>

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>74. Filter Reference - last </summary>

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>75. Filter Reference - length </summary>

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>76. Filter Reference - length_js </summary>

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>77. Filter Reference - linebreaks </summary>

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>78. Filter Reference - linebreaksbr </summary>

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>79. Filter Reference - linenumbers </summary>

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>80. Filter Reference - ljust </summary>

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>81. Filter Reference - lower </summary>

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>82. Filter Reference - make_list </summary>

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>83. Filter Reference - phone2numeric </summary>

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>84. Filter Reference - pluralize </summary>

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>85. Filter Reference - random </summary>

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>86. Filter Reference - rjust </summary>

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>87. Filter Reference - slice </summary>

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>88. Filter Reference - slugify </summary>

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>89. Filter Reference - striptags </summary>

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>90. Filter Reference - time </summary>

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>91. Filter Reference - timesince </summary>

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>92. Filter Reference - timeuntil </summary>

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>93. Filter Reference - title </summary>

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>94. Filter Reference - title </summary>

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>95. Filter Reference - truncatechars </summary>

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>96. Filter Reference - truncatechars_html </summary>

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>97. Filter Reference - truncatewords </summary>

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>98. Filter Reference - truncatewords_html </summary>

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>99. Filter Reference - unordered_list </summary>

```py

```

```py

```

```py

```

```py

```

</details>

<details>
  <summary>100. Filter Reference - upper </summary>

```py

```

```py

```

```py

```

```py

```

</details>
