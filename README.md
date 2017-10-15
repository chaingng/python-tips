# python-tips

respecting [python tutorial](https://docs.python.org/3/tutorial/index.html), 
stock python-tips

for standard objects and modules, see [Python Standard Library](https://docs.python.jp/3/library/index.html#library-index)  
for language reference, see [Python Language Reference](https://docs.python.jp/3/reference/index.html#reference-index)

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

### Numbers
```
>>> 17 / 3  # classic division returns a float
5.666666666666667
>>>
>>> 17 // 3  # floor division discards the fractional part
5
>>> 17 % 3  # the % operator returns the remainder of the division
2
>>> 5 * 3 + 2  # result * divisor + remainder
17
```

```
>>> 5 ** 2  # 5 squared
25
>>> 2 ** 7  # 2 to the power of 7
128
```

### use the last printed expression `-`
```
>>> tax = 12.5 / 100
>>> price = 100.50
>>> price * tax
12.5625
>>> price + _
113.0625
>>> round(_, 2)
113.06
```

### use raw string `r`
```
>>> print('c')
c
>>> print('C:\some\name')
C:\some
ame
>>> print(r'C:\some\name')
C:\some\name
```

### Literal `"""`
```
>>> print("""\
... Usage: thingy [OPTIONS]
...      -h                        Display this usage message
...      -H hostname               Hostname to connect to
... """)
Usage: thingy [OPTIONS]
     -h                        Display this usage message
     -H hostname               Hostname to connect to

```

### String repeated with `*`
```
>>> # 3 times 'un', followed by 'ium'
>>> 3 * 'un' + 'ium'
'unununium'
```

### next to each other are automatically concatenated

```
>>> 'Py' 'thon'
'Python'
```

This only works with two literals though, not with variables or expressions:
```
>>> prefix = 'Py'
>>> prefix 'thon'  # can't concatenate a variable and a string literal
  ...
SyntaxError: invalid syntax
>>> ('un' * 3) 'ium'
  ...
SyntaxError: invalid syntax
```

use `+`
```
>>> prefix + 'thon'
'Python'
```

### use long strings
```
>>> text = ('Put several strings within parentheses '
...         'to have them joined together.')
>>> text
'Put several strings within parentheses to have them joined together.'

```

### String indexed
```
 +---+---+---+---+---+---+
 | P | y | t | h | o | n |
 +---+---+---+---+---+---+
 0   1   2   3   4   5   6
-6  -5  -4  -3  -2  -1
```

### out of range slice indexes are handled gracefully
```
>>> word[4:42]
'on'
>>> word[42:]
''
```

### Strings are immutable
```
>>> word[0] = 'J'
  ...
TypeError: 'str' object does not support item assignment
```

### the length of a string `len()`
```
>>> s = 'supercalifragilisticexpialidocious'
>>> len(s)
34
```

## Lists

### support operations like concatenation
```
>>> squares + [36, 49, 64, 81, 100]
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]

```

### lists are a mutable
```
>>> cubes = [1, 8, 27, 65, 125]  # something's wrong here
>>> 4 ** 3  # the cube of 4 is 64, not 65!
64
>>> cubes[3] = 64  # replace the wrong value
>>> cubes
[1, 8, 27, 64, 125]
```

### add new items
```
>>> cubes.append(343)  # and the cube of 7
>>> cubes
[1, 8, 27, 64, 125, 216, 343]
```

### Assignment to slices is also possible
```
>>> letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g']
>>> letters
['a', 'b', 'c', 'd', 'e', 'f', 'g']
>>> # replace some values
>>> letters[2:5] = ['C', 'D', 'E']
>>> letters
['a', 'b', 'C', 'D', 'E', 'f', 'g']
>>> # now remove them
>>> letters[2:5] = []
>>> letters
['a', 'b', 'f', 'g']
>>> # clear the list by replacing all the elements with an empty list
>>> letters[:] = []
>>> letters
[]
```

### possible to nest lists
```
>>> a = ['a', 'b', 'c']
>>> n = [1, 2, 3]
>>> x = [a, n]
>>> x
[['a', 'b', 'c'], [1, 2, 3]]
>>> x[0]
['a', 'b', 'c']
>>> x[0][1]
'b'
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

