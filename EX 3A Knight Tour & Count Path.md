# EX 3A Knight Tour & Count Path
## DATE: 18-03-2025
## AIM:
To write a python program to find minimum steps to reach to specific cell in minimum moves by knight

## Algorithm
1. Initialize knight's 8 possible moves (dx, dy).
2. Create a queue for BFS. Push the starting position with distance = 0.
3. Mark the starting cell as visited in a 2D visited array.
4. While queue is not empty:
   - Pop the front cell.
   - If it's the target, return its distance.
   - For all 8 possible knight moves:
     - Calculate new (x, y) position.
     - If inside board and not visited:
       - Mark as visited.
       - Push to queue with dist + 1.
5. If target is not reached, return ∞ (not reachable).

## Program:
```
/*
Program to implement to find minimum steps to reach to specific cell in minimum moves by knight.
Developed by: Sowmya V
Register Number: 212222110045
*/

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
    dx = [-2, -1, 1, 2, -2, -1, 1, 2]
    dy = [-1, -2, -2, -1, 1, 2, 2, 1]

    queue = []
    queue.append(cell(knightpos[0], knightpos[1], 0))

    visited = [[False for _ in range(N + 1)] for _ in range(N + 1)]
    visited[knightpos[0]][knightpos[1]] = True

    while len(queue) > 0:
        curr = queue.pop(0)

        if curr.x == targetpos[0] and curr.y == targetpos[1]:
            return curr.dist

        for i in range(8):
            x = curr.x + dx[i]
            y = curr.y + dy[i]

            if isInside(x, y, N) and not visited[x][y]:
                visited[x][y] = True
                queue.append(cell(x, y, curr.dist + 1))

    return float('inf')
    
if __name__=='__main__':
    N = 30
    knightpos = [1, 1]
    targetpos = [30, 30]
    print(minStepToReachTarget(knightpos,
                               targetpos, N))
```
## Output:
![image](https://github.com/user-attachments/assets/61883efd-656a-459a-871e-d21306272044)

## Result:
The program executed successfully, and the minimum number of steps for the knight to reach the target was calculated.
