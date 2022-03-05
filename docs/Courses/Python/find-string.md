---
title: 'Finding a String'
description: 'Python: The Complete Byte [From Zero to One]'
sidebar: 'python'
prev: '/python/'
next: '/python/'
googleid: '<script data-ad-client="ca-pub-8590711166907026" async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>'
---

Finding a String
===
```python
mystring = "Hello World"
print (mystring.count('ll'))
```

    1



```python
print (mystring.count('l'))
```

    3


obviously, "count" method return the number of a search is found wihtin a string
so far as we learned, let's solve a problem from HackerRank at https://www.hackerrank.com/challenges/find-a-string/problem
at first, you may think that using "count" is a straight forward solution but soon you realize not to being true.


```python
#input ABCDCDC, CDC
# output: 2
#trying count will return 1
print("ABCDCDC".count('CDC'))
```

    1


Note that we have "CDC"
- starting position 2 
- starting position 4
- these two results are interlaced. This is the problem
- if they are totaly distinct from each other, the solution using 'count' would work perfectly



```python
# have a look at this
print("ABCDCCDC".count('CDC'))
```

    2



```python
#so here is the solution
def count_substring(string, sub_string):
    count = 0
    str_len = len(string)
    sub_len = len(sub_string)
    
    for x in range (str_len - sub_len + 1):
        scan_string = string[x:x+sub_len]
        if scan_string == sub_string:
            count+= 1
    
    return count

```


```python
count_substring('ABCDCCDC','CDC')
```




    2



commenting the solution
- we iterate over the string moving 1 position at each cycle then compare
- simply our iterating code would be (for x in range (str_len - sub_len + 1) and the results will still work fine but
- note that last iterations wont match at all for all scan_string <  sub_len
- that is why, it is reveal your deep understanding to not enter these loos


```python
mystring ="Hello World"
print( any(char.islower() for char in mystring))
```

    True



```python

```
