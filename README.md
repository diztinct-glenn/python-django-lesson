# python-django-lesson
A beginner's lesson on the Python language and Django framework.

![alt text](https://samueleresca.net/wp-content/uploads/2015/12/python-django-logo.jpg "Python & Django")

#Python#

Python Docs: https://docs.python.org/3/

Python is space sensitive! An indent is 4 spaces. We need to do this so Python knows what code to run if the result is true.

To enter Python in the terminal: Python allows you to specify which version you'd like to run in terminal, so to run Python version 3 we'd enter: `python3`

To exit the Python terminal: `exit()` or `ctrl + d`

Saving a Python file: `filename.py`

Execute Python from Sublime: `python3 filename.py`

making a comment in Python: `#`

You can multiply a string: Example: `"Ola" * 3 = OlaOlaOla`

To make uppercase letter
   ex: `"Ola".upper() = OLA`

Finding the length:
   ex: `len("Ola") = 3  or len(str(1234)) = 4`

Convert something to a string: `str()`

Convert something to an integer: `int()`
<hr/>
####Error Messages####
Error for a variable that has not been defined: NameError

Error for trying to print a key that is not in the dictionary: KeyError

Error that tells you two types can't be compared: TypeError
<hr/>
Lists are objects that are a list of other objects:
    []  ex: lottery=[54, 2,45, 9, 7, 24]

Dictionary is what you call objects stores as a key valued pair:
    {} ex: participant = {'name': 'Jennifer', 'country': 'USA', 'favorite_numbers': [1, 5, 18, 87]}
    print (participant[‘name’])

How to add a new key value pair to the dictionary:
    ex: participant['favorite_language'] = 'Python'

To rearrange from lowest to highest value: `.sort()`

To rearrange from highest to lowest: `.reverse()`

Deleting something from your list: `.pop()`

Comparisons:
    >, <, ==, !=, >=, <=, and(both have to be true), or(only one has to be true)
<hr/>
If Statement:
Example - 
```python
if 3 > 2:
    print('It works!')
```

If Else Statement:
Example - 
```python
if 5 > 2:
    print('5 is indeed greater than 2')
else:
    print('5 is not greater than 2')
```

Elif(Else If) Statement:
Example - 
```python
name = 'Sonja'
if name == 'Ola':
    print('Hey Ola!')
elif name == 'Sonja':
    print('Hey Sonja!')
else:
    print('Hey anonymous!')
```
<hr/>
For loops:
```python
    for ___ in ___:
        def hi(name):
        print('Hi ' + name + '!')
    
    #Example:
    girls = ['Rachel', 'Monica', 'Phoebe', 'Ola', 'You']
    for name in girls:
        hi(name)
        print('Next girl')
```
<hr/>
Range is a function that creates a list of numbers in order:
    Example -
```python
for i in range(1, 6):
    print(i) = 1, 2, 3, 4, 5
```
<hr/>

Virtual Environment will isolate your Python/Django setup on a per-project basis. This means that any changes you make to one website won't affect any others you're also developing.

Trailing commas in lists in Python are always a good habit. We know this goes against everything you learned in JavaScript, but we promise it's alright here in Python land!

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
Django Docs: https://docs.djangoproject.com/en/1.10/

Django is a MTV(Model-Template-View) framework. MTV is similar to what we've seen with MVC in Ruby on Rails except for some small differences. For instance, Views in Django are the bridge between Models(Database) and Templates(What You See), similar to what we called Controllers in Ruby on Rails.

Routes in Django are written using regular expressions

###How to start a project in Django:###
First you need Django installed. You can do that by running
`pip install django`
You can then enter
`django-admin.py startproject project_name ` or `django-admin startproject project_name`
to create a project tree directory. This directory will have certain files/directories in it now, including the: <br>
* project_name root directory - project's root folder<br>
<br>
Inside of that is:<br>
<br>
* manage.py - "Django Admin" used to run commands for project. Similar to app.js in node or App.js in React<br>
* project_name directory stub - holds: <br> 
    * settings.py - settings are stored here<br>
    * urls.py - holds base URLs for our project
    * wsgi.py - controls how project is served at places like Heroku. The entry point from our web server.

###Running the Server:###
From within the project_name directory, not the root directory, run: 
`python manage.py migrate`

This will apply all pending migrations from all apps. Migrations, as we know, are all about the database, which we haven't set up. That's because Django comes with one. Then, run:
`python manage.py runserver 0.0.0.0:8000`
This will run the server.

###How to Write a URL:###
URLs are all written in your urls.py file.

In our urls.py we have to import from what view it is we're using for our route. For example, if we had a views.py file in the same directory as your urls.py we'd write this line:
```python
from . import views
```
Then we'd add what specific "view"(function) it is that we want to load to the url route we specify using regular expressions. So if we had a `hello_world` function in our views.py we could also add this line in our urls.py:
```python
urlpatterns = [
    url(r'^$', views.hello_world) #first: route written in regular expression(this example is a blank string, aka the root), second: the view you're rendering on that route
]
```

###How to Create an App:###
Django projects contain multiple Django apps. Each app generally encompasses a specific area of functionality.

To create an app in Django run this command in your terminal:
`python manage.py startapp app_name`

After we run that command, go into your projects settings.py file and find the part that has the array `INSTALLED_APPS`. After all of the django apps already included in the array, make sure to add whatever you `app_name` was you used in the command `python manage.py startapp app_name`.

###How to Create a Model for your App:###
Just like in Ruby on Rails, in Django, Models are singular.

In the models.py file of our newly created app we'll include this code:
```python
class WhateverIsTheSingularOfYourApp(models.Model): #Our class here will inherit from the base class models.Model because we're making it a Model. (models.Model) is the base class that our models are going to extend.
    created_at = models.DateTimeField(auto_now_add=True) #To add columns to our table we add attributes to our class
    title = models.CharField(max_length=255)
    description = models.TextField()
```

###Adding Instances to Our Model:###
*We'll learn another way to do this further along the tutorial, but for now this will do the trick.*
Run `python manage.py shell` in order to open a Python shell with Django's configuration already loaded.

Within the shell you can run these commands:<br>
To save an in-memory instance of a model to the database: `Model.save()`

To save an in-memory instance of a model to the database and return the newly-created object: `Model.create()`

Run this command to import the model's data to the shell: `from selected_app.models import Model`

Then we can run something like `Model.objects.all()` to list all the things in that specific Model using ORM.

###Creating an App View Using ORM:###
Here's an example of how to set up a basic view listing all the columns in our model for a specific app.

In the _views.py_ file make sure to include this line in order to use data from the model to populate the page:
```python
from .models import Model # importing from .models means to import from the models.py file in the current app's directory
```

Then, still in the _views.py_ file, you could make a function like this example to return a string with all the column names from your Model:
```python
def data_list(request):
  data = Model.objects.all()
  output = ', '.join([str(data) for model in models])
  return HttpResponse(output)
```

Create a _urls.py_ file within the current Apps folder. Within that file include:
```python
from django.conf.urls import url # this allows us to assign urls in our created app
from . import views # this imports the views from the current app directory

urlpatterns = [
    url(r'^$', views.data_list), # this assigns the data_list function within the views.py folder to render the page at the specified route
]
```

Now we've taken care of the url within our specific App's directory, but we're going to need to add some things to the _urls.py_ within our Master App folder.
```python
from django.conf.urls import include # this allows us to use the include function for our url declaration
```
`include()` allows you to include a list of URLs from another module(app). You can pass the function the variable name or a path to the default urlpatterns variable.

We'll also need to add a url path to the `urlpatterns` list for our newly created url in the specific App's folder. Here's an example:
```python
url(r'^data/', include('data.urls'))
```

###Django Admin:###
Django comes built in with a very powerful tool, the Admin. By going to our site's url_/admin_ we're brought to a log in screen that the Django developers were nice enough to give to us. How neat is that?

In order to create a user that is able to login to the Admin area with all permissions we'd run: `python manage.py createsuperuser`

Within our specific App's folder there's an _admin.py_ file. This is where we are going to register our Models to the Admin page. 

First, we have to import our models. We can do that like so:
```python
from .models import Model
```

Then we're going to register that Model to the Admin with this line of code:
```python
admin.site.register(Model) #allows us to edit instances of that model in the admin instead of running shell commands
```

After we save our changes we'll be able to go to our Admin page and log in as a superuser. We should instantly see the Model that we imported/registered to the Admin. From there you'll be able to create new Instances right from the admin page, and not the shell. Score!

###How to Template in Django:###
Convention for saving your templates files is to structure them like so: __app_name/templates/app_name__ because Django looks in app directories for a directory named templates automatically

In our _views.py_ file for __app_name__ we'll have to make sure to include render like so:
`from django.shortcuts import render`

Then let's change our original function to render the way we want so we can template the page the way we want to:
```python
def models_list(request):
  models = Model.objects.all()
  return render(request, 'models/model_list.html', {'models': models})
  # The render function takes three arguments:
  # 1. the request we pass into the actual function
  # 2. the path to the template file (automatically looks at the templates folder within the specific app first so we don't need to include that in the file path)
  # 3. (optional) a context dictionary
```

Then we'll template the __model_list.html__ like so:
```python
{% for model in models %} # this opens the for loop of our Course model using {% %}
<h2>{{ model.title }}</h2> # this add the data from the title column in the Course model using {{}}
{{ model.description }} # this add the data from the description column in the Course model using {{}}

{% endfor %} # this closes the for loop {% %}
```

Everything we've done above is all fine and dandy for templating our pages for apps that we've created, but what if we want to template our root page? Well let's take a look shall we?

First, in the __root folder__(project folder) we'll need to create a templates folder and inside that folder we can create our template file. We could name it something like __home.html__.<br>
Then, we can write whatever HTML we want in our __home.html__ file.<br>
If we go into our __settings.py__ file now we'll see there's a list called _TEMPLATES_. We need to make sure to add something into the __DIRS__ part to let our python app know where to look in order to template our root page. We'll go ahead and add _'templates'_ as an argument.<br>
Finally, we can change our root __views.py__ to this:
```python
from django.shortcuts import render

def home_page(request):
  return render(request, 'home.html')
```
As you can see it's pretty similar to how we template our custom app pages, except for the fact that we need to go into our __settings.py__ and add something.


###Template Inheritance:###
There's a really cool part of templating in Django. They can inherit from other templates! Let's look at an example.<br>

First, in our root folder's templates folder let's add a __layout.html__ file. This file does the same thing our layout.erb file from Rails does.<br>
```html
<!doctype html>
<html>
  <head>
    <title>{% block title %}{% endblock %}</title>
  </head>
  <body>
    {% block content %}{% endblock %}
  </body>
</html>
```

The _block_ tags allow us to override a parent element. We'll get back to what is going on in this file after adding something to our __home.html__ file:
```html
{% extends "layout.html" %} <!-- This line is the equivalent to a yield tag in Rails. It's taking everything from the layout.html file and "extending" it into our homte.html file -->

{% block title %}Howdy!{% endblock %} <!-- The above line of code allows us to write out our title tag(What shows up in the tab of the browser) using these python/django specific tags. -->

{% block content %}<h1>Welcome!</h1>{% endblock %} <!-- This lines up with the block content tags in our layout.html and will render a h1 tag saying "Welcome!" in the body tag.-->
```
###How to Include Static Files:###
At the bottom of our __settings.py__ file we need to add this code:
```python
STATICFILES_DIRS = (
    os.path.join(BASE_DIR, 'assets'), 
)
```
What this does is set the base directory for where our static files will be, which is the __assets__ folder in the root folder.<br>

Now in our root __urls.py__ file we'll add some more things:
```python
from django.contrib.staticfiles.urls import staticfiles_urlpatterns # this will collect static file's urls from each of our applications
    # then after our urlpatterns list,
urlpatterns += staticfiles_urlpatterns()
```

Let's add some of this our templates now so we can actually apply some CSS. In our __layout.html__ file let's go ahead and add these things:
```html
{% load static from staticfiles %} <!-- this is allowing us to use static files in this template -->
<!-- This will go in our <head> tag -->
<link rel="stylesheet" href="{% static 'css/layout.css' %}"> <!-- Here we're just telling the href to use the rules we set above for static files and get the layout.css file out of the css folder in assets -->
```

###Editing our Admin Pages:###
Let's say we have created an app called _courses_. In that app we have our __models.py__ file and in that file this code:
```python
from django.db import models

class Course(models.Model):
    created_at = models.DateTimeField(auto_now_add=True)
    title = models.CharField(max_length=255)
    description = models.TextField()
    
    def __str__(self):
        return self.title

class Step(models.Model):
  title = models.CharField(max_length=255)
  description = models.TextField()
  order = models.IntegerField(default=0)
  course = models.ForeignKey(Course) # this links the Step model to the Course model
  
  def __str__(self):
      return self.title
```

This would make 2 models for us (Course and Step), Course being a course and Step being the steps to that course.<br>

Then in our __admin.py__ of our courses app we'll add these lines:
```python
from django.contrib import admin

from .models import Course, Step # we've got to remember to import all our models we're working with

 # These following 2 classes will allow us to add forms within our specific models admin page.
class StepInline(admin.StackedInline): # StackedInline - inline where fields takes up the full width of the form. TabularInline - inline where fields are part of a single row for the form.
    model = Step
  
class CourseAdmin(admin.ModelAdmin):
    inlines = [StepInline,] #inlines can be thought of as smaller forms within larger forms. The smaller form represents a related record in the database.

admin.site.register(Course, CourseAdmin) # adding CourseAdmin after Course here allows us to use the data from the Step model and render the form.
admin.site.register(Step)
```






