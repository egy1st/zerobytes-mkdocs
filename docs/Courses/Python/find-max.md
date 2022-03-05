---
title: 'Finding Max'
description: 'Python: The Complete Byte [From Zero to One]'
sidebar: 'python'
prev: '/python/'
next: '/python/'
googleid: '<script data-ad-client="ca-pub-8590711166907026" async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>'
---

Finding Max
===

```python
list1, list2 = [555, 700, 100] , ['123', 'xyz', 'zeroBytes', 'abc'], 
print ("Max int value is : ", max(list1) )
print ("Max String value is : ", max(list2) )
```

    Max int value is :  700
    Max String value is :  zeroBytes



```python
import array as arr

# use 'i' for integer & 'd' for float/double/deciaml
arr_int = arr.array('i', [1, 2, 3, 70, 2, 45, 12])
arr_float = arr.array('d', [1, 2.5, 3])

```


```python
max = max(arr_float)
max
```




    3.0




```python
max = arr_int[0]
for i in range(1, len(arr_int)):
    if arr_int[i] > max:
        max = arr_int[i]
        
```


```python
max
```




    70




```python
mylist = []
s = 'append'
d = 1
getattr(mylist, s)(d)
mylist
```




    [1]




```python

```
