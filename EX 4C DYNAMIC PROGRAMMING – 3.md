Skip to content
Navigation Menu
Yuvakrishna0
DAA_Module_22

Code
Issues
Pull requests
Actions
Projects
Security
Insights
DAA_Module_22
/EX 4C DYNAMIC PROGRAMMING – 3.md
Go to file
t
Yuvakrishna0
Yuvakrishna0
Create EX 4C DYNAMIC PROGRAMMING – 3.md
63e6929
 · 
last week
54 lines (37 loc) · 1.48 KB

Preview

Code

Blame
# EX 4C DYNAMIC PROGRAMMING – 3
## DATE:
## AIM:
Given a sequence, find the length of the longest palindromic subsequence in it.

## Algorithm
1.Input the string → Take the string for which you want to find the longest palindromic subsequence.

2.Create a 2D table (dp) → dp[i][j] will store the length of the LPS between index i and j in the string.

3.Initialize → Set all dp[i][i] = 1 because a single character is always a palindrome of length 1.

4.Check substrings of length 2 or more.

5.For every substring:If the characters at the start and end are the same:dp[i][j] = dp[i+1][j-1] + 2

6.If they are different:dp[i][j] = max(dp[i+1][j], dp[i][j-1])

7.The value in dp[0][n-1] (first to last index) is the length of the Longest Palindromic Subsequence.

8.Print the result.  

## Program:
```
# Developed by: SWETHA P
# Register Number: 212222100053

def Lps(X):
    n=len(X)
    dp=[[0 for _ in range(n)] for _ in range(n)]
    
    for x in range(n):
        dp[x][x]=1
        
    for l in range(2,n+1):
        for i in range(n-l+1):
            j=i+l-1
            if X[i]==X[j]:
                dp[i][j]=dp[i+1][j-1]+2
            else:
                dp[i][j]=max(dp[i+1][j],dp[i][j-1])
    return dp[0][n-1]
    
X=input()
print("The length of the LPS is",Lps(X))

```

## Output:

![image](https://github.com/user-attachments/assets/864b0e3e-6b76-4646-a075-fce4bac608a4)

## Result:
Thus the program was executed successfully for finding the length of longest palindromic string.
Copied!
