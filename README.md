# python-tips

**respecting [python tutorial](https://docs.python.org/3/tutorial/index.html) and stock python-tips**

## Reference Docs

for standard objects and modules, see [Python Standard Library](https://docs.python.jp/3/library/index.html#library-index)  
for language reference, see [Python Language Reference](https://docs.python.jp/3/reference/index.html#reference-index)

## Index
- [annotation](https://github.com/chaingng/python-tips/blob/master/annotation.md)
- [break](https://github.com/chaingng/python-tips/blob/master/break.md)
- [condition](https://github.com/chaingng/python-tips/blob/master/condition.md)
- [del](https://github.com/chaingng/python-tips/blob/master/del.md)
- [dict](https://github.com/chaingng/python-tips/blob/master/dict.md)
- [docstring](https://github.com/chaingng/python-tips/blob/master/docstring.md)
- [for](https://github.com/chaingng/python-tips/blob/master/for.md)
- [function](https://github.com/chaingng/python-tips/blob/master/function.md)
- [if](https://github.com/chaingng/python-tips/blob/master/if.md)
- [interpreter](https://github.com/chaingng/python-tips/blob/master/interpreter.md)
- [lambda](https://github.com/chaingng/python-tips/blob/master/lambda.md)
- [lists](https://github.com/chaingng/python-tips/blob/master/list.md)
- [modules](https://github.com/chaingng/python-tips/blob/master/modules.md)
- [numbers](https://github.com/chaingng/python-tips/blob/master/number.md)
- [pass](https://github.com/chaingng/python-tips/blob/master/pass.md)
- [print](https://github.com/chaingng/python-tips/blob/master/print.md)
- [sets](https://github.com/chaingng/python-tips/blob/master/set.md)
- [string](https://github.com/chaingng/python-tips/blob/master/string.md)
- [tuple](https://github.com/chaingng/python-tips/blob/master/tuple.md)
- [range](https://github.com/chaingng/python-tips/blob/master/range.md)


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
