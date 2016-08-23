-----------------------------------------------------------------------------------
1. a = b = [] # make a, b reference to the same list (mutable)
so if a.append(1), then b = [1]
a = b = mutable variables, they are references to the same object
-----------------------------------------------------------------------------------
2. my_list = [[1] * 4] * 3 # my_list = [[1, 1, 1, 1], [1, 1, 1, 1], [1, 1, 1, 1]]
if set my_list[0][0] = 5, then my_list = [[5, 1, 1, 1], [5, 1, 1, 1], [5, 1, 1, 1]]
[x]*3 will make references to the same object if x is mutable
-----------------------------------------------------------------------------------
3. mutable default argument
http://docs.python-guide.org/en/latest/writing/gotchas/
-----------------------------------------------------------------------------------
4. Everything is a reference in Python
http://www.python-course.eu/python3_passing_arguments.php
http://www.tutorialspoint.com/python/python_functions.htm
-----------------------------------------------------------------------------------
5. Unittest
