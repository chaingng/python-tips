# python-tips

**respecting [python tutorial](https://docs.python.org/3/tutorial/index.html), and stock python-tips**

## Reference Docs

for standard objects and modules, see [Python Standard Library](https://docs.python.jp/3/library/index.html#library-index)  
for language reference, see [Python Language Reference](https://docs.python.jp/3/reference/index.html#reference-index)

## Index
- [lists](https://github.com/chaingng/python-tips/blob/master/list.md)
- [sets](https://github.com/chaingng/python-tips/blob/master/set.md)
- [dict](https://github.com/chaingng/python-tips/blob/master/dict.md)
- [tuple](https://github.com/chaingng/python-tips/blob/master/tuple.md)
- [string](https://github.com/chaingng/python-tips/blob/master/string.md)
- [numbers](https://github.com/chaingng/python-tips/blob/master/number.md)
- [function](https://github.com/chaingng/python-tips/blob/master/function.md)
- [modules](https://github.com/chaingng/python-tips/blob/master/modules.md)
- [condition](https://github.com/chaingng/python-tips/blob/master/condition.md)
- [lambda](https://github.com/chaingng/python-tips/blob/master/lambda.md)
- [break](https://github.com/chaingng/python-tips/blob/master/break.md)
- [del](https://github.com/chaingng/python-tips/blob/master/del.md)
- [range](https://github.com/chaingng/python-tips/blob/master/range.md)


## Interpreter

### Run
```
python3.6
```

type ctrl-D to exit.

### Second way to run
```
python -c command [arg]
```

run script and run interpreter, use `-i` to run script.

[Full Command Line Manual](https://docs.python.jp/3/using/cmdline.html#using-on-general)

### Argument Passing
run interpreter with argument, assigned to the argv variable in the sys module.

### Unix Script
on top of the file, add
```
#!/usr/bin/env python3.1
```

### Encoding type
on top of the file, add
```
# -*- coding: encoding -*-
```

## print


```
>>> i = 256*256
>>> print('The value of i is', i)
The value of i is 65536
```

### argument `end` can be used to avoid the newline after the output, or end the output with a different string
```
>>> a, b = 0, 1
>>> while b < 1000:
...     print(b, end=',')
...     a, b = b, a+b
...
1,1,2,3,5,8,13,21,34,55,89,144,233,377,610,987,
```

## if
### elif and else
```
>>> x = int(input("Please enter an integer: "))
Please enter an integer: 42
>>> if x < 0:
...     x = 0
...     print('Negative changed to zero')
... elif x == 0:
...     print('Zero')
... elif x == 1:
...     print('Single')
... else:
...     print('More')
...
More
```

## for
```
>>> # Measure some strings:
... words = ['cat', 'window', 'defenestrate']
>>> for w in words:
...     print(w, len(w))
...
cat 3
window 6
defenestrate 12
```

## If you need to modify the sequence you are iterating over while inside the loop
- use
  - you first make a copy
- why?
  - not safe.
```
>>> for w in words[:]:  # Loop over a slice copy of the entire list.
...     if len(w) > 6:
...         words.insert(0, w)
...
>>> words
['defenestrate', 'cat', 'window', 'defenestrate']
```

## pass

### does nothing
```
>>> while True:
...     pass  # Busy-wait for keyboard interrupt (Ctrl+C)
```


## docstring
```
>>> def my_function():
...     """Do nothing, but document it.
...
...     No, really, it doesn't do anything.
...     """
...     pass
...
>>> print(my_function.__doc__)
Do nothing, but document it.

    No, really, it doesn't do anything.
```

## Annotation
```
>>> def f(ham: str, eggs: str = 'eggs') -> str:
...     print("Annotations:", f.__annotations__)
...     print("Arguments:", ham, eggs)
...     return ham + ' and ' + eggs
...
>>> f('spam')
Annotations: {'ham': <class 'str'>, 'return': <class 'str'>, 'eggs': <class 'str'>}
Arguments: spam eggs
'spam and eggs'
```

## Looping Techniques

### items() for dict
```
>>> knights = {'gallahad': 'the pure', 'robin': 'the brave'}
>>> for k, v in knights.items():
...     print(k, v)
...
gallahad the pure
robin the brave
```

### enumerate() for sequence
```
>>> for i, v in enumerate(['tic', 'tac', 'toe']):
...     print(i, v)
...
0 tic
1 tac
2 toe
```

### zip() for two or more sequences at the same time
```
>>> questions = ['name', 'quest', 'favorite color']
>>> answers = ['lancelot', 'the holy grail', 'blue']
>>> for q, a in zip(questions, answers):
...     print('What is your {0}?  It is {1}.'.format(q, a))
...
What is your name?  It is lancelot.
What is your quest?  It is the holy grail.
What is your favorite color?  It is blue.
```

### To loop over a sequence in reverse, first specify the sequence in a forward direction and then call the reversed() function
```
>>> for i in reversed(range(1, 10, 2)):
...     print(i)
...
9
7
5
3
1
```

### sorted() for sorting while leaving the source unaltered
```
>>> basket = ['apple', 'orange', 'apple', 'pear', 'orange', 'banana']
>>> for f in sorted(set(basket)):
...     print(f)
...
apple
banana
orange
pear
```

###  to change a list while you are looping over it; however, it is often simpler and safer to create a new list instead
```
>>> import math
>>> raw_data = [56.2, float('NaN'), 51.7, 55.3, 52.5, float('NaN'), 47.8]
>>> filtered_data = []
>>> for value in raw_data:
...     if not math.isnan(value):
...         filtered_data.append(value)
...
>>> filtered_data
[56.2, 51.7, 55.3, 52.5, 47.8]
```
