# Address resolution

1. address representation

```
int A[10] = {1,2,3,4,5,6,7,8,9,10};
A[i] = i[A] = *(A + i) = *(i + A)

all resolved to *(A+i)
```

> A is a `int* const` type so value at A can be changed but the A can't point to other address

2. address resolution

```
A[i] = i[A] = *(A + i) = *(i + A)

A[i] = *(A + i*sizeof(*A))
```

```c
int A[5];
// A : 1000
A+1 => A + 1*size(*A) => 1000 + 1*4 = 1004
&A+1 => &A + 1*size(*&A) => 1000 + 1*20 = 1020

int B[2][3];
// B : 2000
B+1 => B + 1*size(*B) => 2000 + 1*size(3 * int*) = 2000 + 1*12 = 2012
&B+1 => &B + 1*size(*&B) => 2000 + 1*size(B) = 2000 + 1*24 = 2024
&B[0]+1 => &B[0] + 1*size(*&B[0]) => 2000 + 1*size(B[0]) => 2000 + 1*12 = 2012
```

3. 2nd resolution

```c
int A[2][3];
// A : 1000
A[1][2] = *(A[1] + 2*sizeof(*A[1]))

A[1] = *(A + sizeof(*A))  // type of A = int**, type *A = int* of size 3 elems = 3*size(int)
     = *(1000 + 3*4)
     = *(1000 + 12) = *(1012)

A[1][2] = *(A[1] + 2*sizeof(*A[1])) // type of A[1] = int* , type *A[1] = int 
        = *(A[1] + 2*sizeof(4))
        = *(1012 + 8) = *(1020)
```

```c
int A[2][3];

A[1][2] = *(A + 1*sizeof(*A))[2]
        = *(*(A + 1*sizeof(*A)) + 2*sizeof(*A[1]))
        = *(*(1000 + 12) + 2*4)
        = *(1000 + 12 + 8) = *(1020)
```

 