# EX 3D Pattern Matching
## DATE: 25/03/2025
## AIM:
To write a python program to implement pattern matching on the given string using Brute Force algorithm.



## Algorithm
1.Start comparing characters from the beginning of both strings s1 and s2.

2.If the characters match, move to the next character in both strings.

3.If there's a mismatch, reset the second string index and shift the first string's index forward by the number of mismatched characters.

4.Continue this process until either the second string is completely matched or the first string ends.

5.If a match is found, return the starting index; otherwise, return 0 to indicate no match.

6.Print the result.
   

## Program:
```
/*
Program to implement the Pattern Matching.
Developed by: LAVANYA S
Register Number: 212223230112
*/
def BF(s1,s2):
    i=0
    j=0
    while(i<len(s1) and j<len(s2)):
        if(s1[i]==s2[j]):
            i+=1
            j+=1
        else:
            i=i-j+1
            j=0
    if(j>=len(s2)):
        return i-len(s2)
    else:
        return 0
if __name__ == "__main__":
    a1=input() 
    a2=input() 
    b=BF(a1,a2)
    print(b)

```

## Output:
![image](https://github.com/user-attachments/assets/1ff41aa0-98e2-4e7e-b331-c0e8862a9301)



## Result:
The brute force substring search program executed successfully and returned the starting index of the match or 0 if no match was found.
