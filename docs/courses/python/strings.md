---
title: 'Strings in Python'
description: 'Python: The Complete Byte [From Zero to One]'
sidebar: 'python'
prev: '/python/'
next: '/python/'
googleid: '<script data-ad-client="ca-pub-8590711166907026" async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>'
---

Strings in Python
=====

```python
mystring = "Hello World"
print (mystring)
```

    Hello World



```python
#Strings in Python are arrays of bytes(charachters), the same it is presented in many programming languages like C++ & Java
for char in mystring:
    print(char)
```

    H
    e
    l
    l
    o
     
    W
    o
    r
    l
    d



```python
#each charachter has its array index
print (mystring[0])
```

    H



```python
print (mystring[-1])
```

    d



```python
# get you string lenght inclus=ding spaces
print(len(mystring))
```

    11



```python
# check substring within the main string
if "Wo" in mystring:
    print ("Found")
else:
    print ("Not Found")
```

    Found



```python
# note that although "Wo" is exist, "wo" is not. search is case senstive
# check substring within the main string
if "wo" in mystring:
    print ("Found")
else:
    print ("Not Found")
```

    Not Found



```python
#even more you can slice a string
print (mystring[1:3])
```

    el



```python
# print last 5 charachters
print (mystring[-5:])
```

    World



```python
# a very common task to do with strings is to change its state amonge Upper-case & Lower-case
print(mystring.upper())
```

    HELLO WORLD



```python
print(mystring.lower())
```

    hello world



```python
# the "strip" method works as "trim" in other languages. 
mystring = " My Name is Mohamed Ali "
print (len(mystring), len(mystring.strip()))
#note that we have one leading space and another tail one at the end, so we have two in total to strip
```

    24 22



```python
# It removes white spaces from the begining and the end but NOT WITHIN a string
# if you intentionally needs to remove all within spaces that would be using join and split as following:
print (("".join(mystring.split())))
```

    HelloWorld



```python
#or simply by replacing each space with null-space as folloing:
print(mystring.replace(" ", ""))
```

    HelloWorld


Now let's solve a problem from Hackerrank at https://www.hackerrank.com/challenges/swap-case/problem


```python
def swap_case(s):
    new_string = ''
    for char in s:
        if char.isupper():
            newchar = char.lower()
        else:
            newchar = char.upper()
            
        new_string +=  newchar   
            
    return new_string

```


```python
#also we may use "swapcase" function which is exactly a staright forward solution
# the solution in return would appear as concise as a "one line return statment"
```


```python
def swap_case(s):
     
    return s.swapcase()
```


```python
swap_case("Hwllo World")
```




    'hWLLO wORLD'



Another problem from hackerRank to solve at https://www.hackerrank.com/challenges/python-string-split-and-join/problem


```python
def split_and_join(line):
    # write your code here
    return  "-".join(line.split())
```


```python
#to concatenate two strings simply use "+"
first_name = "Mohamed"
last_name = "Ali"
print ("My name is: " + first_name + ' ' + last_name )
```

    My name is: Mohamed Ali


a similar problem from HackerRank at https://www.hackerrank.com/challenges/whats-your-name/problem



```python
def print_full_name(first, last):
    # Write your code here
    print ("Hello " + first + ' ' + last + '! You just delved into python.')

```


```python
#another solution using format would appear as folloing:
#where each "%s" refers to a varible of string that comes after "%" consequently

def print_full_name(first, last):
    # Write your code here
    print("Hello %s %s! You just delved into python." % (first,last))
```


```python
print_full_name ("Mohamed", "Ali")
```

    Hello Mohamed Ali! You just delved into python.


also, a problem from HackerRank at https://www.hackerrank.com/challenges/python-mutations/problem
here the solution



```python
def mutate_string(string, position, character):
    string_list = list(string)
    string_list[position] = character
    
    return ''.join(string_list)

```

Note that:
- strings are immutable, you can not change it. Trying mystring[1] = 'M' will trigger an error
- we can convert any string to new list (mutable case) where we can modify as we want
- Finally, we can revert this list to its inital string state using 'join' function


```python
#string slice can also introduce a solution to mentioned problem as folloing
def mutate_string(string, position, character):
        
    return  string[:position]+ character + string[position+1:]
```


```python
mutate_string ('Hello world', 6, "W")
#here we mutated the lower-case 'w' with upper-case one
```




    'Hello World'


