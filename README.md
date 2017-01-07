# python-django-lesson
A beginner's lesson on the Python language and Django framework.

Python is space sensitive!

Routes in Django are written using regular expressions

Virtual Environment will isolate your Python/Django setup on a per-project basis. This means that any changes you make to one website won't affect any others you're also developing.

<h6>How to write a function:</h6>
```python
def functionName(arguments):
    #always indent 4 spaces in Python
    #write your function or define variables inside the function declaration
    return  #return ends the function
```
<h6>How to start a project in Django:</h6>

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
Inside of that is:<br>
* manage.py - "Django Admin" used to run commands for project. Similar to app.js in node or App.js in React<br>
* project_name directory - holds: <br> 
    * settings.py - settings are stored here<br>
    * urls.py - holds base URLs for our project
    * wsgi.py - controls how project is served at places like Heroku. The entry point from our web server.

