# Pointers

a vairable which stores address of other variable

1. *a: value found at value (as address) of a

```c
a = 10 // &a = 1000
*p = &a // &p = 2000 | p = 1000 | *p = 10
```

2. `int *p1[3];` : p1 is a array of int* with 3 elems
3. `int (*p2)[3];` : p2 is a pointer to int array of 3 elems
4. 2d dynamic alloc

```c
int **a; // 4x5
a = (int**)malloc(4*sizeof(int*));

for(int i=0; i<4; i++){
    a[i] = (int*)malloc(5*sizeof(int));
}
```

5. 2nd contiguous array (4x5)

```c
int m = 4, n = 5;

int cont[m*n];

int **arr = (int**)malloc(m*sizeof(int*));
for(int i=0; i<4; i++){
    arr[i] = &cont[i*n];
}
```

6. Type resolution

```c
int *F1(); // func that return int*
int (*F2())[4]; // func that return ptr to an int[4] arr
int (*F3())[3][4]; // func that return ptr to an int[3][4] arr
int (*F4)(char); // func ptr that takes a char and returns int
```

7. triangular array (width 4)

```c
int m = 4;

int total_size = m*(m+1)/2;
int cont[total_size];

int **arr;
arr = (int**)malloc(m*size(int*));
int disp = 0;
for(int i=0; i<m; i++){
    dist += i;
    arr[i] = &cont + disp;
}
```

8. different allocation methods (all same)

```c
int a[4][5];
int *a[4];
int (*a)[5];
int **a;
```

 