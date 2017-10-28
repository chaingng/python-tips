# Dictionaries

- a dictionary as an unordered set of key: value pairs, with the requirement that the keys are unique (within one dictionary).
- indexed by keys, which can be any immutable type; strings and numbers can always be keys.
- Tuples can be used as keys if they contain only strings, numbers, or tuples; if a tuple contains any mutable object either directly or indirectly, it cannot be used as a key
- can’t use lists as keys
- A pair of braces creates an empty dictionary: {}
- possible to delete a key:value pair with del
- an error to extract a value using a non-existent key
- store using a key that is already in use, the old value associated with that key is forgotten

### list(d.keys()) on a dictionary returns a list of all the keys used in the dictionary,
```
>>> tel = {'jack': 4098, 'sape': 4139}
>>> tel['guido'] = 4127
>>> tel
{'sape': 4139, 'guido': 4127, 'jack': 4098}
>>> tel['jack']
4098
>>> del tel['sape']
>>> tel['irv'] = 4127
>>> tel
{'guido': 4127, 'irv': 4127, 'jack': 4098}
>>> list(tel.keys())
['irv', 'guido', 'jack']
>>> sorted(tel.keys())
['guido', 'irv', 'jack']
>>> 'guido' in tel
True
>>> 'jack' not in tel
False
```

###  dict() constructor builds dictionaries directly from sequences of key-value pairs
```
>>> dict([('sape', 4139), ('guido', 4127), ('jack', 4098)])
{'sape': 4139, 'jack': 4098, 'guido': 4127}
```

###  dict comprehensions can be used to create dictionaries from arbitrary key and value expressions
```
>>> {x: x**2 for x in (2, 4, 6)}
{2: 4, 4: 16, 6: 36}
```

### sometimes easier to specify pairs using keyword arguments
```
>>> dict(sape=4139, guido=4127, jack=4098)
{'sape': 4139, 'jack': 4098, 'guido': 4127}

```
