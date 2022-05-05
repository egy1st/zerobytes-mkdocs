---
title: 'getattr vs eval'
description: 'Python: The Complete Byte [From Zero to One]'
sidebar: 'python'
prev: '/python/'
next: '/python/'
googleid: '<script data-ad-client="ca-pub-8590711166907026" async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>'
---

getattr vs eval
====

you can't write object.x, because you don't know in advance which attribute you want (it comes from a string). Very useful for meta-programming.


Objects in Python can have attributes -- data attributes and functions to work with those (methods). Actually, every object has built-in attributes.

For example you have an object person, that has several attributes: name, gender, etc.

You access these attributes (be it methods or data objects) usually writing: person.name, person.gender, person.the_method(), etc.

But what if you don't know the attribute's name at the time you write the program? For example you have attribute's name stored in a variable called attr_name.

if

attr_name = 'gender'
then, instead of writing

gender = person.gender
you can write

gender = getattr(person, attr_name)


```python
class Person():
...     name = 'Victor'
...     def say(self, what):
...         print(self.name, what)
... 
>>> getattr(Person, 'name')
'Victor'
>>> attr_name = 'name'
>>> person = Person()
>>> getattr(person, attr_name)
'Victor'
>>> getattr(person, 'say')('Hello')
Victor Hello
```


      File "<ipython-input-1-c0033f5de77d>", line 13
        Victor Hello
                   ^
    SyntaxError: invalid syntax




```python
x= hash((1,2)
x
```


      File "<ipython-input-5-b45d1d86958e>", line 2
        x
        ^
    SyntaxError: invalid syntax




```python

```
