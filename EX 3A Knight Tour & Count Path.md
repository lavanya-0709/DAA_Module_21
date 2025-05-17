# EX 3A Knight Tour & Count Path
## DATE: 15/03/2025
## AIM:
To write a python program to find minimum steps to reach to specific cell in minimum moves by knight


## Algorithm
1.Start from the knight’s initial position and mark it as visited.

2.Use a queue (BFS approach) to explore all valid moves from the current position.

3.For each move, check if the new position is inside the board and not yet visited.

4.If the new position is the target, return the number of moves taken to reach it.

5.Otherwise, add the new position to the queue with incremented move count.

6.Repeat until the queue is empty or the target is found. 
   

## Program:
```
/*
Program to implement to find minimum steps to reach to specific cell in minimum moves by knight.
Developed by: LAVANYA S
Register Number: 212223230112 
*/
from collections import deque
class cell:
     
    def __init__(self, x = 0, y = 0, dist = 0):
        self.x = x
        self.y = y
        self.dist = dist

def isInside(x, y, N):
    if (x >= 1 and x <= N and
        y >= 1 and y <= N):
        return True
    return False
def minStepToReachTarget(knightpos,
                         targetpos, N):
    moves=[(2,1),(1,2),(-1,2),(-2,1),(-2,-1),(-1,-2),(1,-2),(2,-1)]
    queue=deque([cell(knightpos[0],knightpos[1],0)])
    visited=[[False for _ in range(N+1)] for _ in range(N+1)]
    visited[knightpos[0]][knightpos[1]]=True
    while queue:
        cur=queue.popleft()
        if(cur.x,cur.y)==(targetpos[0],targetpos[1]):
            return cur.dist
        for dx,dy in moves:
            nx,ny=cur.x+dx,cur.y+dy
            if isInside(nx,ny,N) and not visited[nx][ny]:
                visited[nx][ny]=True
                queue.append(cell(nx,ny,cur.dist+1))
    return -1 
     
    # add your code here
    
if __name__=='__main__':
    N = 30
    knightpos = [1, 1]
    targetpos = [30, 30]
    print(minStepToReachTarget(knightpos,
                               targetpos, N))
```

## Output:
![image](https://github.com/user-attachments/assets/963e8439-e96d-4d04-9898-2be9c3b46578)



## Result:
The program executed successfully, and the minimum number of steps for the knight to reach the target was calculated.
