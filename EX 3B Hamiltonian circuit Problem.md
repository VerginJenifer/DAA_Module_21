# EX 3B Hamiltonian Circuit Problem
## DATE:
## AIM:
To write a python program to check whether Hamiltonian path exits in the given graph.

## Algorithm
1. Use a DP table `dp[node][mask]` to store whether a path ending at `node` with visited set `mask` is possible.
2. Initialize each node as a starting point with only itself visited.
3. For each subset of nodes (mask), and for each node `j` in that subset, check if any neighbor `k` can lead to `j`.
4. If such a neighbor exists and the path to `k` exists without `j`, mark `dp[j][mask]` as True.
5. After filling DP, if any `dp[i][all_visited_mask]` is True, a Hamiltonian path exists.  

## Program:
```
/*
Program to implement to check whether Hamiltonian path exits in the given graph.
Developed by: D Vergin Jenifer
Register Number: 212223240174
def Hamiltonian_path(adj, N):
    dp = [[False for i in range(1 << N)] for j in range(N)]
    for i in range(N):
        dp[i][1 << i] = True
    for i in range(1 << N):
        for j in range(N):
            if ((i & (1 << j)) != 0):
 
                for k in range(N):
                    if ((i & (1 << k)) != 0 and
                             adj[k][j] == 1 and
                                     j != k and
                          dp[k][i ^ (1 << j)]):
                        dp[j][i] = True
                        break
    for i in range(N):
        if (dp[i][(1 << N) - 1]):
            return True
    return False
adj = [ [ 0, 1, 1, 1, 0 ] ,
        [ 1, 0, 1, 0, 1 ],
        [ 1, 1, 0, 1, 1 ],
        [ 1, 0, 1, 0, 0 ] ]
 
N = len(adj)
 
if (Hamiltonian_path(adj, N)):
    print("YES")
else:
    print("NO")
*/
```

## Output:

![image](https://github.com/user-attachments/assets/5544d204-76e5-4e62-be53-3844cb79c7f9)


## Result:
The Hamiltonian path program executed successfully, and it determined whether a Hamiltonian path exists in the given graph.
