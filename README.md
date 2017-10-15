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

### String epeated with `*`
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

