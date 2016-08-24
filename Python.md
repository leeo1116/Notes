###1. Mutable objects
```python
a = b = [] # make a, b reference to the same list (mutable)
# so if a.append(1), then b = [1]
# a = b = mutable variables, they are references to the same object

my_list = [[1] * 4] * 3 # my_list = [[1, 1, 1, 1], [1, 1, 1, 1], [1, 1, 1, 1]]
# if set my_list[0][0] = 5, then my_list = [[5, 1, 1, 1], [5, 1, 1, 1], [5, 1, 1, 1]]
# [x]*3 will make references to the same object if x is mutable
```
###2. [Mutable default argument](http://docs.python-guide.org/en/latest/writing/gotchas/)

###3. Everything is a reference in Python 
  + [passing arguments](http://www.python-course.eu/python3_passing_arguments.php)
  + [tutorialspoint](http://www.tutorialspoint.com/python/python_functions.htm)

###4. Unittest
```python
a = Mock()
# a.b.c is a Mock() object
# a.b.c.return_value is a Mock() object
my_class.my_class_method.return_value.my_another_class_method.return_value = 1  # first approach
my_class.my_class_method().my_another_class_method.return_value = 1  # second approach
# first approach is equivalent to second approach, and no need to declear:
my_class.my_class_method.return_value = Mock()
# [cause sth.return_value will create a new Mock() object](https://docs.python.org/3.4/library/unittest.mock.html#the-mock-class)
```
