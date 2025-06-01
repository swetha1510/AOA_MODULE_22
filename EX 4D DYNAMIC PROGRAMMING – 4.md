# EX 4D DYNAMIC PROGRAMMING – 4
## DATE:
## AIM:
To find the minimum number of operations to convert str1 to str2 using Naive recursive method.

## Algorithm
1.Take two words as input.

2.If one word is empty → return the length of the other word (just insert or delete all letters).

3.If last letters of both words are same → move to the rest of the words.

4.If last letters are different → Changing a letter, Adding a letter, Removing a letter

5.Repeat until both words are finished.

6.Print the smallest number of steps to change one word into the other.
## Program:
```
# Developed by: SWETHA P
# Register Number: 212222100053

def ed(x,y,m,n):
    if m==0:
        return n
    if n==0:
        return m
    if x[m-1]==y[n-1]:
        return ed(x,y,m-1,n-1)
    return 1+min(ed(x,y,m-1,n-1),ed(x,y,m,n-1),ed(x,y,m-1,n))
    
x=input()
y=input()
print("Edit Distance",ed(x,y,len(x),len(y)))
```

## Output:
![image](https://github.com/user-attachments/assets/2b276bd1-20e4-4935-81d2-91c4b1b65cf8)

## Result:
Thus the program was executed successfully for finding edit distance between two strings.
