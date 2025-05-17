# EX 3B Hamiltonian Circuit Problem
## DATE: 18/03/2025
## AIM:
To write a python program to check whether Hamiltonian path exits in the given graph.

## Algorithm
1.Try each vertex as a possible starting point for the path.

2.From the current vertex, move to any unvisited adjacent vertex.

3.Keep adding valid vertices to the path until all N vertices are included.

4.If a complete path is formed without revisiting vertices, return True.

5.If stuck (no valid next move), backtrack to explore other possibilities.

6.If no complete path is found from any starting point, return False. 
  

## Program:
```
/*
Program to implement to check whether Hamiltonian path exits in the given graph.
Developed by: LAVANYA S
Register Number: 212223230112
*/
def Hamiltonian_path(adj, N):
    path = [-1] * N
    for i in range(N):
        path[0] = i
        pos = 1
        while pos >=0:
            if pos == N:
                return True
            found = False
            for v in range(N):
                if adj[path[pos-1]][v]==1 and v not in path[:pos]:
                    path[pos] = v
                    pos+=1
                    found = True
                    break
            if not found:
                pos-=1
    return False
    ######################### Add your Code here ##########################
adj = [ [ 0, 1, 1, 1, 0 ] ,
        [ 1, 0, 1, 0, 1 ],
        [ 1, 1, 0, 1, 1 ],
        [ 1, 0, 1, 0, 0 ] ]
 
N = len(adj)
 
if (Hamiltonian_path(adj, N)):
    print("YES")
else:
    print("NO")
```

## Output:

![image](https://github.com/user-attachments/assets/5dbf30b9-2d0c-4705-a442-8d14a86b0927)


## Result:
The Hamiltonian path program executed successfully, and it determined whether a Hamiltonian path exists in the given graph.
