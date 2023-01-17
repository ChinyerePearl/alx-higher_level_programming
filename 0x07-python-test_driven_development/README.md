# 0x07. Python - Test-driven development
 Foundations - Higher-level programming ― Python

## 0. Integers addition  [ 0-add_integer.py, tests/0-add_integer.txt ]  
  Write a function that adds 2 integers.
  * Prototype: [ def add_integer(a, b=98): ]
  * a and b must be integers or floats, otherwise raise a TypeError exception with the message a must be an integer or b must be an integer
  * a and b must be first casted to integers if they are float
  * Returns an integer: the addition of a and b
  > python3 -m doctest -v ./tests/0-add_integer.txt | tail -2
  > python3 -c 'print(__import__("0-add_integer").__doc__)' | wc -l
  > python3 -c 'print(__import__("0-add_integer").add_integer.__doc__)' | wc -l

## 1. Divide a matrix  [ 2-matrix_divided.py, tests/2-matrix_divided.txt ]
  Write a function that divides all elements of a matrix.
  * [ Prototype: def matrix_divided(matrix, div): ]
  ** matrix must be a list of lists of integers or floats, otherwise raise a TypeError exception with the message matrix must be a matrix (list of lists) of integers/floats
  * Each row of the matrix must be of the same size, otherwise raise a TypeError exception with the message Each row of the matrix must have the same size
  * div must be a number (integer or float), otherwise raise a TypeError exception with the message div must be a number
  * div can’t be equal to 0, otherwise raise a ZeroDivisionError exception with the message division by zero
  * All elements of the matrix should be divided by div, rounded to 2 decimal places
  * Returns a new matrix
  > ./2-main.py
  > python3 -m doctest -v ./tests/2-matrix_divided.txt | tail -2
  + Note: you might have a different number of tests than in the above example. As usual, your tests should cover all possible cases.

## 2. Say my name  [ 3-say_my_name.py, tests/3-say_my_name.txt ]
  Write a function that prints My name is <first name> <last name>
  * Prototype: [ def say_my_name(first_name, last_name=""): ]
  * first_name and last_name must be strings otherwise, raise a TypeError exception with the message first_name must be a string or last_name must be a string
  > ./3-main.py | cat -e
  > python3 -m doctest -v ./tests/3-say_my_name.txt | tail -2
  + Note: you might have a different number of tests than in the above example. As usual, your tests should cover all possible cases.
  
## 3. Print square  [ 4-print_square.py, tests/4-print_square.txt ]
  Write a function that prints a square with the character #.
  * Prototype: [ def print_square(size): ]
  * size is the size length of the square
  * size must be an integer, otherwise raise a TypeError exception with the message size must be an integer
  * if size is less than 0, raise a ValueError exception with the message size must be >= 0
  * if size is a float and is less than 0, raise a TypeError exception with the message size must be an integer
  > ./4-main.py 
  > python3 -m doctest -v ./tests/4-print_square.txt

## 4. Text indentation [ 5-text_indentation.py, tests/5-text_indentation.txt ]
  Write a function that prints a text with 2 new lines after each of these characters: ., ? and :
  * Prototype: [ def text_indentation(text): ]
  * text must be a string, otherwise raise a TypeError exception with the message text must be a string
  * There should be no space at the beginning or at the end of each printed line
  > ./5-main.py | cat -e
  > python3 -m doctest -v ./tests/5-text_indentation.txt

## 5. Max integer - Unittest  [ tests/6-max_integer_test.py ]
  Since the beginning you have been creating “Interactive tests”. For this exercise, you will add Unittests.
  In this task, you will write unittests for the function [ def max_integer(list=[]): ].
  * Your test file should be inside a folder tests
  * You have to use the [unittest module](https://docs.python.org/3.4/library/unittest.html#module-unittest)
  * Your test file should be python files (extension: .py)
  * Your test file should be executed by using this command: python3 -m unittest tests.6-max_integer_test
  * All tests you make must be passable by the function below
  * We strongly encourage you to work together on test cases, so that you don’t miss any edge case  
  > python3 -m unittest tests.6-max_integer_test 2>&1 | tail -1
  > head -7 tests/6-max_integer_test.py 

## 6. Matrix multiplication  [ 100-matrix_mul.py, tests/100-matrix_mul.txt ]
  Write a function that multiplies 2 matrices:
  * Read: [Matrix multiplication - only Matrix product (two matrices)](https://en.wikipedia.org/wiki/Matrix_multiplication)
  * Prototype: [ def matrix_mul(m_a, m_b): ]
  * m_a and m_b must be validated with these requirements in this order
  * m_a and m_b must be an list of lists of integers or floats:
  + if m_a or m_b is not a list: raise a TypeError exception with the message m_a must be a list or m_b must be a list
  + if m_a or m_b is not a list of lists: raise a TypeError exception with the message m_a must be a list of lists or m_b must be a list of lists
  + if m_a or m_b is empty (it means: = [] or = [[]]): raise a ValueError exception with the message m_a can't be empty or m_b can't be empty
  + if one element of those list of lists is not an integer or a float: raise a TypeError exception with the message m_a should contain only integers or floats or m_b should contain only integers or floats
  + if m_a or m_b is not a rectangle (all ‘rows’ should be of the same size): raise a TypeError exception with the message each row of m_a must be of the same size or each row of m_b must be of the same size
  * If m_a and m_b can’t be multiplied: raise a ValueError exception with the message m_a and m_b can't be multiplied
  > ./100-main.py 
  > python3 -m doctest -v ./tests/100-matrix_mul.txt | tail -2

## 7. Lazy matrix multiplication  [ 101-lazy_matrix_mul.py, tests/101-lazy_matrix_mul.txt ]
  Write a function that multiplies 2 matrices by using the module NumPy
  To install it: [ pip3 install numpy==1.15.0 ]
  * Prototype: [ def lazy_matrix_mul(m_a, m_b): ]
  * Test cases should be the same as 100-matrix_mul but with new exception type/message
  > ./101-main.py
  > python3 -m doctest -v ./tests/101-lazy_matrix_mul.txt 
  
## 8. CPython #3: Python Strings  [ 102-python.c ]
  Create a function that prints Python strings.
  * Prototype: [ void print_python_string(PyObject *p); ] Format:
  * If p is not a valid string, print an error message (see example)
  * Read: [Unicode HOWTO](https://docs.python.org/3.4/howto/unicode.html)   
###About:
  * Python version: 3.4
  * You are allowed to use the C standard library
  * Your shared library will be compiled with this command line: [gcc -Wall -Wextra -pedantic -Werror -std=c99 -shared -Wl,-soname,libPython.so -o libPython.so -fPIC -I/usr/include/python3.4 102-python.c ]
+
```
@ubuntu:~/0x07. Pyhton Strings$ cat 102-tests.py
import ctypes

lib = ctypes.CDLL('./libPython.so')
lib.print_python_string.argtypes = [ctypes.py_object]
s = "The spoon does not exist"
lib.print_python_string(s)
s = "ложка не существует"
lib.print_python_string(s)
s = "La cuillère n'existe pas"
lib.print_python_string(s)
s = "勺孨"
lib.print_python_string(s)
s = "숟가락은 존재하지 않는다."
lib.print_python_string(s)
s = "スプーンは存在しない"
lib.print_python_string(s)
s = b"The spoon does not exist"
lib.print_python_string(s)
@ubuntu:~/0x07. Pyhton Strings$ gcc -Wall -Wextra -pedantic -Werror -std=c99 -shared -Wl,-soname,libPython.so -o libPython.so -fPIC -I/usr/include/python3.4 102-python.c
@ubuntu:~/0x07. Pyhton Strings$ python3 ./102-tests.py
[.] string object info
  type: compact ascii
  length: 24
  value: The spoon does not exist
[.] string object info
  type: compact unicode object
  length: 19
  value: ложка не существует
[.] string object info
  type: compact unicode object
  length: 24
  value: La cuillère n'existe pas
[.] string object info
  type: compact unicode object
  length: 5
  value: 勺孨
[.] string object info
  type: compact unicode object
  length: 14
  value: 숟가락은 존재하지 않는다.
[.] string object info
  type: compact unicode object
  length: 10
  value: スプーンは存在しない
[.] string object info
  [ERROR] Invalid String Object
@ubuntu:~/0x07. Pyhton Strings$ 
```
+
+

## READNG

* [doctest — Test interactive Python examples](https://docs.python.org/3.4/library/doctest.html) 
* [doctest – Testing through documentation](https://alx-intranet.hbtn.io/rltoken/96kLRRIOHzsn3VDDXT21HA)
* [Unit Tests in Python](https://www.youtube.com/watch?v=1Lfv5tUGsn8) 
* [CPython](https://github.com/python/cpython)
* [Code review: string concatenation in C](https://blog.holbertonschool.com/code-review-string-concatenation-in-c/)
* [Hack The Virtual Memory: C strings & /proc](https://blog.holbertonschool.com/hack-the-virtual-memory-c-strings-proc/)
* [Hack The Virtual Memory: Python bytes](https://blog.holbertonschool.com/hack-the-virtual-memory-python-bytes/)
* [Hack the Virtual Memory: drawing the VM diagram](https://blog.holbertonschool.com/hack-the-virtual-memory-drawing-the-vm-diagram/)
* [Hack the Virtual Memory: malloc, the heap & the program break](https://blog.holbertonschool.com/hack-the-virtual-memory-malloc-the-heap-the-program-break/)
* [Embedding Python in Your C Programs](https://www.linuxjournal.com/article/8497)
* [Embedding Python in C/C++](https://learning-python.com/class/Workbook/unit16.htm)
* [Porting Extension Modules to 3.0](https://wiki.python.org/moin/PortingExtensionModulesToPy3k)
* [Python | C Strings of Doubtful Encoding | Set-1](https://www.geeksforgeeks.org/python-c-strings-of-doubtful-encoding-set-1/)
* [Python - Extension Programming with C](https://www.tutorialspoint.com/python/python_further_extensions.htm)
* [Python: get string representation of PyObject?](https://stackoverflow.com/questions/5356773/python-get-string-representation-of-pyobject)
* [The internals of Python string interning](http://guilload.com/python-string-interning/)
* [Documentation » Python/C API Reference Manual](https://docs.python.org/3/c-api/veryhigh.html)
* [Unicode Strings Passing to C Libraries](https://www.geeksforgeeks.org/unicode-strings-passing-to-c-libraries/)
* [Unicode HOWTO](https://docs.python.org/3/howto/unicode.html)


## Notes ...

1. you should always write the documentation (module(s) + function(s)) and tests first, before you actually code anything
2. Don’t trust the user, always think about all possible edge cases
> python -m doctest -v example.txt
> python3 -m doctest -v ./tests/0-add_integer.txt | tail -2
> python3 -c 'print(__import__("0-add_integer").__doc__)' | wc -l
> python3 -c 'print(__import__("0-add_integer").add_integer.__doc__)' | wc -l
