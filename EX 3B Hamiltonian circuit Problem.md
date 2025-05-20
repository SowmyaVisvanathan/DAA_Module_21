# EX 3B Hamiltonian Circuit Problem
## DATE: 18-04-2025
## AIM:
To write a python program to check whether Hamiltonian path exits in the given graph.

## Algorithm
1. Start path from vertex 0.
2. Use recursion to try adding each unvisited vertex that is adjacent to the last vertex in the path.
3. At each step (pos):
   - If pos == N, a valid Hamiltonian path is found → return True.
   - Else, for each vertex v from 0 to N-1:
     - If v is adjacent to last vertex in path (adj[path[pos-1]][v] == 1) and v is not already in path:
       - Add v to current path.
       - Recurse to next position.
       - If it returns True, propagate result.
       - Else, backtrack (path[pos] = -1).
4. If no path is found after trying all options → return False.

## Program:
```
/*
Program to implement to check whether Hamiltonian path exits in the given graph.
Developed by: Sowmya V
Register Number: 212222110045
*/

def Hamiltonian_path(adj, N):
    def is_hamiltonian_path(path, pos):
        if pos == N:
            return True
        for v in range(N):
            if adj[path[pos - 1]][v] == 1 and v not in path:
                path[pos] = v
                if is_hamiltonian_path(path, pos + 1):
                    return True
                path[pos] = -1
        return False
    path = [-1] * N
    path[0] = 0
    if not is_hamiltonian_path(path, 1):
        return False
    return True
    
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
![image](https://github.com/user-attachments/assets/72c3319a-7d91-4600-bc49-65a87e8304cb)

## Result:
The Hamiltonian path program executed successfully, and it determined whether a Hamiltonian path exists in the given graph.
