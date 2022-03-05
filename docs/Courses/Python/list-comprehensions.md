---
title: 'List Comprehensions'
description: 'Python: The Complete Byte [From Zero to One]'
sidebar: 'python'
prev: '/python/'
next: '/python/'
googleid: '<script data-ad-client="ca-pub-8590711166907026" async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>'
---

List Comprehensions
====


```python
a, b, c, n = [int(input()) for _ in range(4)]
```

    1
    2
    3
    4



```python
print ([[x,y,z] for x in range(a + 1) for y in range(b + 1) for z in range(c + 1) if x + y + z != n])
```

    [[0, 0, 0], [0, 0, 1], [0, 0, 2], [0, 0, 3], [0, 1, 0], [0, 1, 1], [0, 1, 2], [0, 2, 0], [0, 2, 1], [0, 2, 3], [1, 0, 0], [1, 0, 1], [1, 0, 2], [1, 1, 0], [1, 1, 1], [1, 1, 3], [1, 2, 0], [1, 2, 2], [1, 2, 3]]



```python

```
