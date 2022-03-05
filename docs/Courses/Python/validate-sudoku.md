---
title: 'How to Validate Sudoku Squares in Python'
description: 'Python: The Complete Byte [From Zero to One]'
sidebar: 'python'
prev: '/python/'
next: '/python/'
googleid: '<script data-ad-client="ca-pub-8590711166907026" async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>'
---

How to Validate Sudoku Squares in Python
=====


Here, we are going to solve a probem from LeetCode at https://leetcode.com/problems/valid-sudoku/


```python
myboard = [[".",".",".",".","5",".",".","1","."],
[".","4",".","3",".",".",".",".","."],
[".",".",".",".",".","3",".",".","1"],
["8",".",".",".",".",".",".","2","."],
[".",".","2",".","7",".",".",".","."],
[".","1","5",".",".",".",".",".","."],
[".",".",".",".",".","2",".",".","."],
[".","2",".","9",".",".",".",".","."],
[".",".","4",".",".",".",".",".","."]]
```


```python
def isValidSudoku(board) -> bool:
    
    for x in range(9):
        my_list=[]
        for y in range (9):
            num = board[x][y]
            if num.isnumeric():
                if num not in my_list:
                    my_list.append(num)
                else:
                    return False
            
    for x in range(9):
        my_list=[]
        for y in range (9):
            num = board[y][x]
            if num.isnumeric():
                if num not in my_list:
                    my_list.append(num)
                else:
                    return False
                     
                        
    for row_start in range (0,9,3):
        for col_start in range (0,9,3):
            
            my_list=[]
            for x in range(row_start, row_start+3):
                for y in range (col_start, col_start+3):
                    num = board[y][x]
                    if num.isnumeric():
                        if num not in my_list:
                            my_list.append(num)
                        else:
                            return False
                      

    return True
```


```python
isValidSudoku(myboard)
```




    False



Algorithm Analysis
- Lines 3-11: we iterate over all rows to check if there are any duplicates numbers in any row
- Lines 13-21: we iterate over all columns to check if there are any duplicates numbers in any column
- Lines 24-35: we iterate over all 3x3 boxes to check if there are any duplicates numbers in any 3x3 box



What you may learn from that solution:
- use  isnumeric() method to check if a string is valid number or not (lines 7, 17, 31)
- use append method to add value to the end of list
- use (if, in) to check if value exist in a list i.e (if num in my_list)
- use (not) to negate the condition i.e ( (if num not in my_list)

Range Parameters:
- **start**: (Optional) An integer to start counting from, defaults to 0.
- **stop**: An integer to stop the count at.
- **step**: (Optional) An integer that indicates the incremental value from start parameter value, defaults to 1.


```python
for n in range (0,9,3):
    print (n, end=' ')
```

    0 3 6 

### Another solution using Bitmasking

- we can use values at different positions of an array to mark whether the number corresponding to each position has been seen or not. 
- Each position in the array can take a value of 0 or 1, which can be represented by a single bit. 
- This will resul in improving the space complexity.
- We can use a binary number with 9 digits to represent whether numbers 1 through 9 have been visited or not.


```python
def isValidSudoku(board) -> bool:
    N = 9
    # Use binary number to check previous occurrence
    rows = [0] * N
    cols = [0] * N
    boxes = [0] * N

    for r in range(N):
        for c in range(N):
            # Check if the position is filled with number
            if board[r][c] == ".":
                continue

            pos = int(board[r][c]) - 1

            # Check the row
            if rows[r] & (1 << pos):
                return False
            rows[r] |= (1 << pos)

            # Check the column
            if cols[c] & (1 << pos):
                return False
            cols[c] |= (1 << pos)

            # Check the box
            idx = (r // 3) * 3 + c // 3
            if boxes[idx] & (1 << pos):
                return False
            boxes[idx] |= (1 << pos)

    return True
```


```python
isValidSudoku(myboard)
```




    False


