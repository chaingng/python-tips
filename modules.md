# Modules

## get name
```
>>> fibo.__name__
'fibo'
```

## assign it to a local name
```
>>> fib = fibo.fib
>>> fib(500)
1 1 2 3 5 8 13 21 34 55 89 144 233 377
```

## imports names from a module directly into the importing module’s symbol table
```
>>> from fibo import fib, fib2
>>> fib(500)
1 1 2 3 5 8 13 21 34 55 89 144 233 377
```

## import all names that a module defines
```
>>> from fibo import *
>>> fib(500)
1 1 2 3 5 8 13 21 34 55 89 144 233 377
```

## executing modules as scripts with the __name__ set to "__main__"
```
python fibo.py <arguments>
```

## make the file usable as a script as well as an importable module
```
if __name__ == "__main__":
    import sys
    fib(int(sys.argv[1]))

```

## The Module Search Path `spam.py`
1.  the interpreter first searches for a built-in module with that name
1. searches for a file named spam.py in a list of directories given by the variable sys.path

### sys.path is initialized from these locations
```
- The directory containing the input script (or the current directory when no file is specified).
- PYTHONPATH (a list of directory names, with the same syntax as the shell variable PATH).
- The installation-dependent default.
```

