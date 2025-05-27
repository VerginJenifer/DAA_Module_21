# EX 3D Pattern Matching
## DATE:
## AIM:
To write a python program to implement pattern matching on the given string using Brute Force algorithm.



## Algorithm
1. Slide the pattern `s2` over text `s1` from index 0 to n - m.
2. For each index, check if the substring of `s1` matches `s2`.
3. Compare character by character in the inner loop.
4. If all characters match, return the starting index.
5. If no match is found by the end, return -1.

## Program:
```
/*
Program to implement the Pattern Matching.
Developed by: D Vergin Jenifer
Register Number: 212223240174
def BF(s1,s2):
    n=len(s1)
    m=len(s2)
    for i in range(n-m+1):
        match=True
        for j in range(m):
            if s1[i+j]!=s2[j]:
                match= False
                break
        if match:
            return i
    return -1
if __name__ == "__main__":
    a1=input() 
    a2=input() 
    b=BF(a1,a2)
    print(b) 
*/
```

## Output:

![image](https://github.com/user-attachments/assets/e9a53133-52e5-4afb-8858-9046f84e508d)


## Result:
The brute force substring search program executed successfully and returned the starting index of the match or 0 if no match was found.
