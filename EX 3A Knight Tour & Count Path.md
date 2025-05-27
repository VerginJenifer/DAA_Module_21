# EX 3A Knight Tour & Count Path
## DATE:
## AIM:
To write a python program to find minimum steps to reach to specific cell in minimum moves by knight


## Algorithm
1. Use BFS starting from the knight's position, with distance initialized to 0.
2. At each step, explore all 8 possible knight moves.
3. For each valid and unvisited position, mark it visited and enqueue it with dist+1.
4. If the target is reached during traversal, return the current distance.
5. If queue is empty and target not reached, return -1 (though unreachable case is rare).  

## Program:
```
/*
Program to implement to find minimum steps to reach to specific cell in minimum moves by knight.
Developed by: D Vergin Jenifer
Register Number: 212223240174
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
def minStepToReachTarget(knightpos,targetpos, N):
    dx=[1,2,-1,-2,1,2,-1,-2]
    dy=[2,1,-2,-1,-2,-1,2,1]
    visited=[[False for _ in range(N+1)]for _ in range(N+1)]
    q=deque()
    q.append(cell(knightpos[0],knightpos[1],0))
    visited[knightpos[0]][knightpos[1]]=True
    while q:
        t=q.popleft()
        if t.x==targetpos[0] and t.y==targetpos[1]:
            return t.dist
        for i in range(8):
            x=t.x+dx[i]
            y=t.y+dy[i]
            if isInside(x,y,N) and not visited[x][y]:
                visited[x][y]=True
                q.append(cell(x,y,t.dist+1))
    return -1
    
if __name__=='__main__':
    N = 30
    knightpos = [1, 1]
    targetpos = [30, 30]
    print(minStepToReachTarget(knightpos,
                               targetpos, N))
*/
```

## Output:

![image](https://github.com/user-attachments/assets/baa1cf34-d867-46e3-b5ae-df8ca7fdd010)


## Result:
The program executed successfully, and the minimum number of steps for the knight to reach the target was calculated.
