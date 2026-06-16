# Const

where a value can't change

```c
int x = 10;
int* p = &x;
```

```c
x can be const // variable value can't be changed
p can be const // address can't be changed
*p can be const // value at the address can't be changed
```

```c
// non-const variable
int a = 10, b = 20, c = 30;
a = 100; //ok

// const variable
const int x; // error
const int x = 10, y = 20; // ok
y = 30; // error

// non-const pointer
int *p1;
p1 = &a, p1 = &b, *p1 = 50; // ok
p1 = &x, p1 = &y; // error : variable is const but can be changed by pointer so it gives error

// const pointer (value of p2 can be changed but value at *p2 can't)
const int *p2;
p2 = &a, p2 = &b; // ok : const pointer have variable data so its ok cause it can't change value
p2 = &x, p2 = &y; // ok : const pointer have const data so its ok cause nobody can change value
*p2 = 20; // error : can't change value stored at address which p2 have

int* const cp1; // error : const variable not assigned value
int* const cp1 = &a; // ok : value assigned to const on init
int* const cp2 = &x; // error : address at cp2 can't be changed
cp1 = &b; // error : address at cp2 can't be changed
*cp1 = 20; // ok

const int* const cpc1; // error : no init
const int* const cpc1 = &a; // ok
const int* const cpc1 = &b; // ok
const int* const cpc1 = &x; // ok
const int* const cpc1 = &y; // ok
cpc1 = &a; // error : no re-init
*cpc1 = 10; // error : no value change
```


| int a              | Meaning                             |
| ------------------ | ----------------------------------- |
| int a              | nothing is constant                 |
| int* const a       | value of "a" is constant            |
| const int* a       | value pointed to by "a" is constant |
| const int* const a | value of "a" and at "a" is constant |


---

## Addition and Subtraction from Pointers

1. Addition

```c
int *p,*q;
p++; // ok
p +=10; // ok : if in range
p += q // error : no pointer to pointer addition
```

2. Subtraction

```c
int *p,*q;
p--; // ok
p -=20; // ok : if in range
p -= q // ok : if p and q are of same type
```

3. Multiplication and Division

`not allowed`