---
title: 'Nested Lists'
description: 'Python: The Complete Byte [From Zero to One]'
sidebar: 'python'
prev: '/python/'
next: '/python/'
googleid: '<script data-ad-client="ca-pub-8590711166907026" async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>'
---

Nested Lists
====


A nested list is a list that contains another list, in other words it is a list of lists. It is also referred to as a multi-diminsional array.


```python
nested_list = [['John', '50'], ['Mark', '40'], ['Ali', '24']]
print (len(nested_list))
#note that lenght of this nested list is 3, since we have 3 inner lists within the outer one
```

    3



```python
print (nested_list[0])
```

    ['John', '50']



```python
print (nested_list[2][0])
```

    Ali



```python
# Let's iterate over this nested lists
for inner in nested_list:
    print (inner)
```

    ['John', '50']
    ['Mark', '40']
    ['Ali', '24']



```python
# let's check value of inner so far
inner
```




    ['Ali', '24']




```python
 # then let's iterate over all values within last nested list which is stored in the variable 'inner' at the moment
for value in inner:
    print (value)
```

    Ali
    24



```python
# Now let's iterate over all values within last nested list which is stored in the variable 'inner' at the moment
for inner in nested_list:
    for value in inner:
        print (value)
    
```

    John
    50
    Mark
    40
    Ali
    24


Here we solve a solution for a problem from HackerRank at https://www.hackerrank.com/challenges/nested-list/problem
the problem is an application on the use of nested list 


```python
# Let's initiate a dictionary so, all names that share the same score can be listed under the same key
score_dic = {}

for _ in range(int(input())):
    name = input()
    score = float(input())
    if score in score_dic:
        score_dic[score].append(name)
    else:
        score_dic[score] = [name]

# We need to convert that dictionary to new list sorted on keys
score_list = list(score_dic.items())
score_list.sort()
next_min = score_list[1][1]

# if we have mutltiple names then sort them alphabetically
next_min.sort()

# print the output by unzip the results using *
print (*next_min, sep = "\n")

```
