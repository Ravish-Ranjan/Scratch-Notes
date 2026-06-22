# Memos Note

 

# Aroha Company

1. what they so : firmware for soc for routers
2. What they require :

```
OA
Network
OS
    bankers algo
    deadlock avoidence
    deadlock prevention
    memory management
Quant
linux commands
proc IOCTL
build automations
DSA
```

3. Interviews

```
Technical Round 1
    basic questions (**past interview questions**)
    most C lang
```

```
Technical Round 2
```

```
HR Round
```

[https://www.geeksforgeeks.org/interview-experiences/quiz-corner-gq/](https://www.geeksforgeeks.org/interview-experiences/quiz-corner-gq/)
#company

---

# Dynamic Prog

```
approach (memoization)
    func(data, memo):
        if (basecase)
             return memo[wanted]
        if (memo[current]):
             return memo[current]

        modify memo based on current 
        return func(data,memo)
```

---

# Bit Manipulation

```
if ds is array
    and no order is given 
    and array has duplicates ->
        use bit manipulation with xor
```

`a^b = c`  
`a^c = b`

to get xor separation if candicates are known  
use & operator with least significant set bit

---

# **Staircase Problem**

ways[i] = ways[i-1] + ways[i-2]

ways[i for i <=3] = i

---

# **Undirected Graph Cycle Detection**

maintain the visited and parent array and if child is visited and current's parent is not that child then their is a cycle

---

# Binary Search on Rotated Array

we can use binary search here by following following rules  
at a time either left or right is sorted but one and only one part is confirmed sorted

```
if low <= high
    if mid == key
        return mid
    if left part is sorted (arr[low] <= arr[mid])
        if element in left part
            set high = mid - 1 : (go in left part)
        else 
            set low = mid + 1 : (go in right part)
    else (right part is sorted)
        if element in right part
            set low = mid + 1 : (go in right part)
        else 
            set high = mid - 1 : (go int left part)
not found
```

 