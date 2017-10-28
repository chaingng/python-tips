# print


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
