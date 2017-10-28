# String

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
