# EX 2C BACKTRACKING- SUBSET SUM PROBLEM
## DATE: 29-04-2025
## AIM:
To demonstrate that the sum of the subset of a given set is equal to the given sum.


## Algorithm
1. Start the program.
2. Input the number of elements n in the set.
3. Read n integer values from the user and store them in a list arr.
4. Input the target sum value x. 
5. Define a function subsetSum(n, arr, x):.
6. Call the function subsetSum(n, arr, x) to check and print all valid subsets.  
7. End the program.

## Program:
```
/*
Program to implement Subset sum problem.
Developed by: Vishinu H
Register Number: 212223220124
*/

from itertools import combinations
def subsetSum(n,arr,x):
    for i in range(n+1):
        for subset in combinations(arr,i):
            if sum(subset) == x:
                print(list(subset))

n=int(input())
arr=[]
for i in range(0,n):
    a=int(input())
    arr.append(a)
x = int(input())

subsetSum(n, arr, x)

```

## Output:
![image](https://github.com/user-attachments/assets/99a107b7-0a16-404b-abfa-f110bedaa545)



## Result:
The Subset Sum program executed successfully, and the result was determined based on whether a subset matching the target sum was found or not.
