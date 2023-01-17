# 0x0C. Python - Almost a circle
 Foundations - Higher-level programming ― Python
 
## Requirements
...........................
      Python Scripts
...........................

* Allowed editors: vi, vim, emacs
* All your files will be interpreted/compiled on Ubuntu 14.04 LTS using python3 (version 3.4.3)
* All your files should end with a new line
* The first line of all your files should be exactly #!/usr/bin/python3
* A README.md file, at the root of the folder of the project, is mandatory
* Your code should use the PEP 8 style (version 1.7.*)
* All your files must be executable
* The length of your files will be tested using wc
* All your modules should be documented: python3 -c 'print(__import__("my_module").__doc__)'
* All your classes should be documented: python3 -c 'print(__import__("my_module").MyClass.__doc__)'
* All your functions (inside and outside a class) should be documented: python3 -c 'print(__import__("my_module").my_function.__doc__)' and python3 -c 'print(__import__("my_module").MyClass.my_function.__doc__)'
* A documentation is not a simple word, it’s a real sentence explaining what’s the purpose of the module, class or method (the length of it will be verified)

All your files, classes and methods must be unit tested and be PEP 8 validated.

> python3 -m unittest discover tests 

## 0. If it's not tested it doesn't work  [  ]


## 9. Update #1  [ models/rectangle.py ]

  Update the class Rectangle by updating the public method [ def update(self, *args): ] by changing the prototype to [ update(self, *args, **kwargs) ] that assigns a key/value argument to attributes:

  * [**kwargs] can be thought of as a double pointer to a dictionary: key/value
  + As Python doesn’t have pointers, **kwargs is not literally a double pointer – describing it as such is just a way of explaining its behavior in terms you’re already familiar with
  * [**kwargs] must be skipped if [*args] exists and is not empty
  * Each key in this dictionary represents an attribute to the instance
  + This type of argument is called a “key-worded argument”. Argument order is not important

## 10. And now, the Square!  []

## 15. Dictionary to JSON string
  JSON is one of the standard formats for sharing data representation.
  Update the class Base by adding the static method [ def to_json_string(list_dictionaries): ] that returns the JSON string representation of list_dictionaries:
  * list_dictionaries is a list of dictionaries
  * If list_dictionaries is None or empty, return the string: "[]"
  * Otherwise, return the JSON string representation of list_dictionaries

