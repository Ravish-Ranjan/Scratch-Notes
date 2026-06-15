# Operators Quirks

1. + has higher preccedence than << (shift)
2. i = i++ has unextected behaviour
3. only printf, () evaluated expression in them not sizeof

```c
a = 20
x = (a += 10) // x = 30
```

4. (, , ,) evaluates expression left tot right

```c
a = 5
b = ++a + a++; // compiler dependent
```


| Precedence | Category       | Operators                                               | Description                                                                                                      | Associativity |
| ---------- | -------------- | ------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- | ------------- |
| **1**      | Postfix        | `()` `[]` `.` `->` `++` `--`                            | Function call, array subscript, member access, member access via pointer, postfix increment/decrement            | Left-to-right |
| **2**      | Unary          | `+` `-` `!` `~` `++` `--` `*` `&` `(type)` `sizeof`     | Unary plus/minus, logical NOT, bitwise NOT, prefix increment/decrement, dereference, address-of, type cast, size | Right-to-left |
| **3**      | Multiplicative | `*` `/` `%`                                             | Multiplication, division, remainder (modulus)                                                                    | Left-to-right |
| **4**      | Additive       | `+` `-`                                                 | Addition and subtraction                                                                                         | Left-to-right |
| **5**      | Bitwise Shift  | `<<` `>>`                                               | Bitwise left shift and right shift                                                                               | Left-to-right |
| **6**      | Relational     | `<` `<=` `>` `>=`                                       | Less than, less than or equal, greater than, greater than or equal                                               | Left-to-right |
| **7**      | Equality       | `==` `!=`                                               | Relational equal to and not equal to                                                                             | Left-to-right |
| **8**      | Bitwise AND    | `&`                                                     | Bitwise AND                                                                                                      | Left-to-right |
| **9**      | Bitwise XOR    | `^`                                                     | Bitwise exclusive OR                                                                                             | Left-to-right |
| **10**     | Bitwise OR     | `|`                                                     | Bitwise inclusive OR                                                                                             | Left-to-right |
| **11**     | Logical AND    | `&&`                                                    | Logical AND (supports short-circuiting)                                                                          | Left-to-right |
| **12**     | Logical OR     | `||`                                                    | Logical OR (supports short-circuiting)                                                                           | Left-to-right |
| **13**     | Conditional    | `?:`                                                    | Ternary conditional                                                                                              | Right-to-left |
| **14**     | Assignment     | `=` `+=` `-=` `*=` `/=` `%=` `<<=` `>>=` `&=` `^=` `|=` | Simple and compound assignments                                                                                  | Right-to-left |
| **15**     | Comma          | `,`                                                     | Comma separator                                                                                                  | Left-to-right |


5. function call compier dependent

```c
x = func1() + func2(); // compiler dependent which function to call first
```

6. assignment

```c
int a = 1,2,3; //error
int x;
x = 1,2,3; // no error x = 1
```

7. increments

```c
++x => {  
    x = x+1; // doesnt happends instantly, can happen anytime before semicolon and after calling
    return x;
} return x variable value after incrementing

x++ => {
    y = x;
    return y;
    x = x+1; //doesnt happends instantly, can happen anytime before semicolon and after calling
} return x variable value before incrementing
```

```c
int x = 5;
++x = 10; // error 6 = 10
x++ = 10; // error 5 = 10 
```

 