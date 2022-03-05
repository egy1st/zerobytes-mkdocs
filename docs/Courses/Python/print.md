---
title: 'Print Method'
description: 'Python: The Complete Byte [From Zero to One]'
sidebar: 'python'
prev: '/python/'
next: '/python/'
googleid: '<script data-ad-client="ca-pub-8590711166907026" async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>'
---

Print Function
====

It is a common programming habit to start teaching any programming language with little code that allows you to salute the world, just to say "Hello World!" in your programming language flavour.


```python
print("Hello World!")
```

    Hello World!


Also, you may assign "Hello World!" to a variable then pass it to the print method


```python
my_string = "Hello World!"
print(my_string)
```

    Hello World!



```python
print('hello, world!'.title())
```

    Hello, World!


Another solution is to assign each word to a variable then print both of them. Actually, this seems to be not visible but it is just for the sake of mastering how the method works.


```python
var1, var2 = 'Hello', 'World!'
print (var1)
print (var2)
```

    Hello
    World!


but we need to align them together on the same line


```python
print (var1, var2, sep=' ')
```

    Hello World!


Method Signature:
- print(*values, sep=' ', end='\n', file=sys.stdout)
- print(value1, value2, value3, sep=' ', end='\n', file=sys.stdout)

where:
- **sep** is the delimiter between values.
- **end** is what to be printed after values.
- **file** is the output stream.

Now, let us solve a problem from HackerRank
https://www.hackerrank.com/challenges/python-print/problem


```python
n = int(input())
for x in range(1, n+1):
        print (x, end='')
```

    7
    1234567

Note since the required solution expect results to be adjacent to each other, we set the 'end' parameter to '' instead of its defulat value '\n' which force a new line


```python

```
