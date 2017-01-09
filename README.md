# python-django-lesson
A beginner's lesson on the Python language and Django framework.

![alt text](https://samueleresca.net/wp-content/uploads/2015/12/python-django-logo.jpg "Python & Django")

Python Docs: https://docs.python.org/3/tutorial/datastructures.html

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

####Error Messages####
Error for a variable that has not been defined: NameError

Error for trying to print a key that is not in the dictionary: KeyError

Error that tells you two types can't be compared: TypeError

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
`include()` allows you to include a list of URLs from another module(app). You can pass the method the variable name or a path to the default urlpatterns variable.

We'll also need to add a url path to the `urlpatterns` list for our newly created url in the specific App's folder. Here's an example:
```python
url(r'^data/', include('data.urls'))
```
  
  



