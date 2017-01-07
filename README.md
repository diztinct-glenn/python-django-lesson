# python-django-lesson
A beginner's lesson on the Python language and Django framework.

<<<<<<< HEAD
Python Docs: https://docs.python.org/3/tutorial/datastructures.html

Python is space sensitive!

To enter Python in the terminal: 
    python3

To exit the Python terminal:
    exit() or control + z

Saving a Python file:
    filename.py (.py extension)

Execute Python from Sublime:
    python3 filename.py

An indent is 4 spaces. We need to do this so Python knows what code to run if the result is true.

making a commeny in Python:
    #

You can multiply a string:
    ex: "Ola" * 3 = OlaOlaOla

To use apostrophes:
   ex: "Runnin' in the forest" or 'Runnin/' in the forest'

To make uppercase letter
   ex: "Ola".upper() = OLA

Finding the length:
   ex: len("Ola") = 3  or len(str(1234)) = 4

Convert anything to a string
    str()

Convert anything to an integer: (We can't necessarily convert text into numbers – what would int('hello') be anyway?)
    int()

Error for a variable that has not been defined:
    NameError

Function to print variables:
    print(name_of_function)

Lists are objects that are a list of other objects:
    []  ex: lottery=[54, 2,45, 9, 7, 24]

To rearrange from lowest to highest value:
    .sort()  ex: lottery.sort()

To rearrange from highest to lowest:
    .reverse()

Index is the number that says where in a list an item occurs. This starts at 0 as well.
    [] ex: print(lottery[0])

Deleting something from your list: 
    .pop()

Dictionary is what you call objects stores as a key valued pair:
    {} ex: participant = {'name': 'Jennifer', 'country': 'USA', 'favorite_numbers': [1, 5, 18, 87]}
    print (participant[‘name’])

Error for trying to print a key that is not in the dictionary:
    KeyError

How to add a new key value pair to the dictionary:
    ex: participant['favorite_language'] = 'Python'

Comparisons:
    >, <, ==, !=, >=, <=, and(both have to be true), or(only one has to be true)

Error that tells you two types can't be compared:
    TypeError

Boolean have to be typed this way:
    True, False (true, tRue, false, and fALSE will not work)

If statement:
    ex: if 3 > 2:
            print('It works!')

if else statement:
    ex: if 5 > 2:
            print('5 is indeed greater than 2')
        else:
            print('5 is not greater than 2')

elif statement:
    ex: name = 'Sonja'
        if name == 'Ola':
            print('Hey Ola!')
        elif name == 'Sonja':
            print('Hey Sonja!')
        else:
            print('Hey anonymous!')

Writing a function in Python:
    def  ex: def
            def hi(name):
                if name == 'Ola':
                    print('Hi Ola!')
                elif name == 'Sonja':
                    print('Hi Sonja!')
                else:
                    print('Hi anonymous!')
    hi()

Foor loops:
    for ___ in ___:
        def hi(name):
        print('Hi ' + name + '!')

    girls = ['Rachel', 'Monica', 'Phoebe', 'Ola', 'You']
    for name in girls:
        hi(name)
        print('Next girl')

Range is a function that creates a list of numbers in order:
    ex: for i in range(1, 6):
        print(i) = 1, 2, 3, 4, 5
=======
![alt text](https://samueleresca.net/wp-content/uploads/2015/12/python-django-logo.jpg "Python & Django")

#Python#
Python is space sensitive!

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
    url(r'^$', views.hello_world)
]
```

###How to Create an App:###
Django projects contain multiple Django apps. Each app generally encompasses a specific area of functionality.

To create an app in Django run this command in your terminal:
`python manage.py startapp app_name`

After we run that command, go into your projects settings.py file and find the part that has the array `INSTALLED_APPS`. After all of the django apps already included in the array, make sure to add whatever you `app_name` was you used in the command `python manage.py startapp app_name`.







>>>>>>> f95d1fbc179cb91eb4603b17aa8322a777f6ff9e


