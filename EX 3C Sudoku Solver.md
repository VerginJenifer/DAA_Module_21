# EX 3C Sudoku Solver
## DATE:
## AIM:
To write a python program to find the solution of sudoku puzzle using Backtracking.


## Algorithm
1. For each empty cell, try placing digits from 1 to 9.
2. For each digit, check if it’s safe in row, column, and 3×3 subgrid.
3. If safe, place the digit and recursively solve the rest of the board.
4. If no digit fits, backtrack and reset the cell to 0.
5. If the board is completely filled, print the solution.  

## Program:
```
/*
Program to implement to to find the solution of sudoku puzzle using Backtracking.
Developed by: D Vergin Jenifer
Register Number: 212223240174
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
                        if solve():
                            return True
                        board[i][j]=0
                return False
    printBoard(board)
    return True

                    
solve()
*/
```

## Output:

![image](https://github.com/user-attachments/assets/82153982-c461-4cd4-aa74-202d2ac4ecc3)


## Result:
The Sudoku solver program executed successfully and found the solution for the given puzzle.
