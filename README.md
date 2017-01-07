# python-django-lesson
A beginner's lesson on the Python language and Django framework.
![alt text](https://samueleresca.net/wp-content/uploads/2015/12/python-django-logo.jpg "Python & Django")

#Python#
Python is space sensitive!

Virtual Environment will isolate your Python/Django setup on a per-project basis. This means that any changes you make to one website won't affect any others you're also developing.

###How to write a function:###
```python
def functionName(arguments):
    #always indent 4 spaces in Python
    #write your function or define variables inside the function declaration
    return  #return ends the function
```

###Importing packages:###
Example:
```python
from django.http import HttpResponse #from package.subpackage import module 

def hello_world(request):
  return HttpResponse('Hello World')
```

#Django#
Django is a MTV(Model-Template-View) framework. MTV is similar to what we've seen with MVC in Ruby on Rails except for some small differences. For instance, Views in Django are the bridge between Models(Database) and Templates(What You See), similar to what we called Controllers in Ruby on Rails.

Routes in Django are written using regular expressions

###How to start a project in Django:###
First you need Django installed. You can do that by running
```
pip install django
```
You can then enter
```
django-admin.py startproject project_name 
```
or 
```
django-admin startproject project_name
```
to create a project tree directory. This directory will have certain files/directories in it now, including the: <br>
* project_name root directory - project's root folder<br>
<br>
Inside of that is:<br>
<br>
* manage.py - "Django Admin" used to run commands for project. Similar to app.js in node or App.js in React<br>
* project_name directory - holds: <br> 
    * settings.py - settings are stored here<br>
    * urls.py - holds base URLs for our project
    * wsgi.py - controls how project is served at places like Heroku. The entry point from our web server.

###Running the Server:###

From within the project_name directory, not the root directory, run: 
```
python manage.py migrate
```
This will apply all pending migrations from all apps. Migrations, as we know, are all about the database, which we haven't set up. That's because Django comes with one. Then, run:
```
python manage.py runserver 0.0.0.0:8000
```
This will run the server.
