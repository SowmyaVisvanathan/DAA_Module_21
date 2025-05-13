# EX 3C Sudoku Solver
## DATE: 25-04-2025
## AIM:
To write a python program to find the solution of sudoku puzzle using Backtracking.

## Algorithm
1. 
2. 
3. 
4.  
5.   

## Program:
```
/*
Program to implement to to find the solution of sudoku puzzle using Backtracking.
Developed by: Sowmya V
Register Number: 212222110045
*/
board = [
    [0, 0, 0, 8, 0, 0, 4, 0, 3],
    [2, 0, 0, 0, 0, 4, 8, 9, 0],
    [0, 9, 0, 0, 0, 0, 0, 0, 2],
    [0, 0, 0, 0, 2, 9, 0, 1, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 7, 0, 6, 5, 0, 0, 0, 0],
    [9, 0, 0, 0, 0, 0, 0, 8, 0],
    [0, 6, 2, 7, 0, 0, 0, 0, 1],
    [4, 0, 3, 0, 0, 6, 0, 0, 0]
]

def printBoard(board):
    for i in range(0, 9):
        for j in range(0, 9):
            print(board[i][j], end=" ")
        print()

def isPossible(board, row, col, val):
    for j in range(0, 9):
        if board[row][j] == val:
            return False

    for i in range(0, 9):
        if board[i][col] == val:
            return False

    startRow = (row // 3) * 3
    startCol = (col // 3) * 3
    for i in range(0, 3):
        for j in range(0, 3):
            if board[startRow+i][startCol+j] == val:
                return False
    return True

def solve():
    for i in range(0,9):
        for j in range(0,9):
            if board[i][j]==0:
                for val in range(1,10):
                    if isPossible(board,i,j,val):
                        board[i][j]=val
                        solve()
                        board[i][j]=0
                return
    printBoard(board)
solve()
```
## Output:
![image](https://github.com/user-attachments/assets/304d5e4b-e86d-4eba-85fc-8b478277015a)

## Result:
The Sudoku solver program executed successfully and found the solution for the given puzzle.
