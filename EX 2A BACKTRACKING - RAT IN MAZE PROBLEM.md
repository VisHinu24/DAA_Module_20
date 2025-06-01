# EX 2A BACKTRACKING - RAT IN MAZE PROBLEM
## DATE: 29-04-2025
## AIM:
To implement the Rat in a Maze problem using backtracking and find all possible paths from the start to the destination in a given maze.


## Algorithm
1. Start the program and define the maze as a 2D list where 1 indicates a path and 0 indicates a blocked cell.
2. Define a function isSafe(maze, x, y).
3. Create a solution matrix sol[N][N], initialized with all zeros.
4. Define a recursive utility function solveMazeUtil(maze, x, y, sol)
5. Define the main function solveMaze(maze).
6. End the program.  

## Program:
```
/*
Program to implement Rat in a Maze.
Developed by: Vishinu H
Register Number: 212223220124  
*/

N = 4
 

def printSolution( sol ):
     
    for i in sol:
        for j in i:
            print(str(j) + " ", end ="")
        print("")
 

def isSafe( maze, x, y ):
     
    if x >= 0 and x < N and y >= 0 and y < N and maze[x][y] == 1:
        return True
     
    return False
 

def solveMaze( maze ):
     
    # Creating a 4 * 4 2-D list
    sol = [ [ 0 for j in range(4) ] for i in range(4) ]
     
    if solveMazeUtil(maze, 0, 0, sol) == False:
        print("Solution doesn't exist");
        return False
     
    printSolution(sol)
    return True
     

def solveMazeUtil(maze, x, y, sol):
    if x == N-1 and y==N-1:
        sol[x][y]=1
        return True
    if isSafe(maze,x,y)==True:
        sol[x][y]=1
        if solveMazeUtil(maze,x+1,y,sol)==True:
            return True
        if solveMazeUtil(maze,x,y+1,sol)==True:
            return True
        sol[x][y]=0
        return False
    return False



# Driver program to test above function
if __name__ == "__main__":
    # Initialising the maze
    maze = [ [1, 0, 0, 0],
             [1, 1, 0, 1],
             [0, 1, 0, 0],
             [1, 1, 1, 1] ]
              
    solveMaze(maze)
```

## Output:
![image](https://github.com/user-attachments/assets/3a5716c5-597b-4b00-a8da-fc68011db7d4)



## Result:
The Rat in a Maze program executed successfully, and a valid path from the start to the destination was found and display.
