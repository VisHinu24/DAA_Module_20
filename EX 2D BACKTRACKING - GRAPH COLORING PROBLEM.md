# EX 2D BACKTRACKING - GRAPH COLORING PROBLEM
## DATE: 29-04-2025
## AIM:
To solve the Graph Coloring Problem using backtracking, assigning colors to the vertices of a graph such that no two adjacent vertices share the same color while minimizing the number of colors used.



## Algorithm
1. Start the program and define the number of vertices V in the graph and the adjacency matrix graph[V][V].
2. Input the maximum number of colors m that can be used to color the graph.
3. Define a function isSafe(v, colour, c):.
4. Define a recursive function graphColourUtil(m, colour, v):.
5. Define the main function graphColouring(m):.
6. End the program.  

## Program:
```
/*
Program to implement Graph Coloring Problem using backtracking.
Developed by: Vishinu H
Register Number:  212223220124
*/

class Graph():
 
    def __init__(self, vertices):
        self.V = vertices
        self.graph = [[0 for column in range(vertices)]for row in range(vertices)]
 
  
    def isSafe(self, v, colour, c):
        for i in range(self.V):
            if self.graph[v][i] == 1 and colour[i] == c:
                return False
        return True
     
    
    def graphColourUtil(self, m, colour, v):
        if v == self.V:
            return True
        for c in range(1, m + 1):
            if self.isSafe(v, colour, c):
                colour[v] = c
                if self.graphColourUtil(m, colour, v + 1):
                    return True
                colour[v] = 0
        return False
 
    def graphColouring(self, m):
        colour = [0] * self.V
        if not self.graphColourUtil(m, colour, 0):
             return False
        print ("Solution exist and Following are the assigned colours:")
        for c in colour:
            print (c,end=' ')
        return True

```

## Output:
![image](https://github.com/user-attachments/assets/48dcb752-89e9-42f4-aa66-81423e27df4b)



## Result:
The Graph Coloring program executed successfully, and the colors were assigned to the vertices such that no two adjacent vertices share the same color.
