# EX 3D Pattern Matching
## DATE: 22-04-2025
## AIM:
To write a python program to implement pattern matching on the given string using Brute Force algorithm.



## Algorithm
1. 
2. 
3. 
4.  
5.   

## Program:
```
/*
Program to implement the Pattern Matching.
Developed by: Sowmya V
Register Number: 212222110045
*/

def BF(s1,s2):
    n = len(s1)
    m = len(s2)
    
    for i in range(n - m + 1):
        j = 0
        while j < m and s1[i + j] == s2[j]:
            j += 1
        if j == m:
            return i
    return -1
if __name__ == "__main__":
    a1=input() 
    a2=input() 
    b=BF(a1,a2)
    print(b)

```

## Output:
![image](https://github.com/user-attachments/assets/3bd024ae-e0ad-4a3d-931f-3565b9934229)

## Result:
The brute force substring search program executed successfully and returned the starting index of the match or 0 if no match was found.
