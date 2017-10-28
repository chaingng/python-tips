# range()


```
>>> for i in range(5):
...     print(i)
...
0
1
2
3
4
```

### to specify a different increment
```
range(5, 10)
   5 through 9

range(0, 10, 3)
   0, 3, 6, 9

range(-10, -100, -30)
  -10, -40, -70
```

### A strange thing happens if you just print a range
- why?
  - It is an object which returns the successive items of the desired sequence when you iterate over it, but it doesn’t really make the list, thus saving space

```
>>> print(range(10))
range(0, 10)
```

### creates lists from iterables
```
>>> list(range(5))
[0, 1, 2, 3, 4]
```
