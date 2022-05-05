---
title: 'Read Input'
description: 'Python: The Complete Byte [From Zero to One]'
sidebar: 'python'
prev: '/python/'
next: '/python/'
googleid: '<script data-ad-client="ca-pub-8590711166907026" async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>'
---

How to Read an Input
====

```python
# we expect a string
x = input()
x
```

    Mohamed Ali





    'Mohamed Ali'




```python
# we still expect a string
x = input()
x
```

    12





    '12'




```python
# we expect an integer
x = int(input())
x
```

    12





    12




```python
# we still expect an integer
x = int(input())
x
```

    12.0



    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-4-bcb160fc4d9d> in <module>
          1 # we still expect an integer
    ----> 2 x = int(input())
          3 x


    ValueError: invalid literal for int() with base 10: '12.0'



```python
# we expect a float/decimal/double
x = float (input())
x
```

    12.0





    12.0




```python
# we still expect a float/decimal/double
x = float (input())
x
```

    12





    12.0




```python
# read multiple entries at once
a, b, c, d = [int(input()) for _ in range(4)]
```

    1
    2
    3
    4



```python
a
```




    1




```python
b
```




    2




```python
c
```




    3




```python
d
```




    4




```python
# read multiple entries at once
v = [int(input()) for _ in range(4)]
```

    1
    2
    3
    4



```python
v
```




    [1, 2, 3, 4]




```python
arr = map(int, input().split())
```

    1 2 3 4



```python
list(arr)
```




    [1, 2, 3, 4]




```python

```
