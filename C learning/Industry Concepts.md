# Industry Concepts

1. **loop jamming**
  - In loop jamming, the bodies of the two loops are merged together to form a single loop provided that they do not make any references to each other.

```c
// before
for (int i = 0; i < n; i++) {
    A[i] = B[i] + C[i];
}

for (int i = 0; i < n; i++) {
    D[i] = A[i] * 2;
}
```

```c
//after
for (int i = 0; i < n; i++) {
    A[i] = B[i] + C[i];
    D[i] = A[i] * 2;
}
```

2. **loop concatenation**
  - the bodies of the two loops are concatenated together to form a series of loop, loop concatenation, some times help to reduce complexity.

```c
// before
for (int i = 0; i < n; i++) {
    A[i] = i;
}

for (int i = 0; i < m; i++) {
    B[i] = i * 2;
}
```

```c
// after
for (int i = 0; i < n + m; i++) {
    if (i < n)
        A[i] = i;
    else
        B[i - n] = (i - n) * 2;
}
```

3. **loop unrolling**
  - we try to optimize a program's execution speed. It is also known as space–time tradeoff.

```c
// before
for(int i = 0; i < n; i++) {
    sum += i;
}
```

```c
// after
for(int i = 0; i < n; i+=2) {
    sum += i;
    sum += i+1;
}
```

4. **strength reduction**
  - compiler optimize expensive operations with equivalent but less expensive operations.

 