# python-django-lesson
A beginner's lesson on the Python language and Django framework.

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


