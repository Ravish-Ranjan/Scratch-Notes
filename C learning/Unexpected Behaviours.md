# Unexpected Behaviours

1. no default params
2. char size

```c
char c = 'A';
sizeof(c); // 1 : explicitly defined char -> 1 byte
sizeof('A'); // implecity 'A' is converted to 65 which is int and treated as 4 bytes int
```

3. string ptr sizeof

```c
char s[n];
sizeof(*s) = sizeof(value at s address) = sizeof(char) = 1
```

4. switch case only takes int (char implecitylt int so it too)
5. globally declared int auto defined to 0
6. in switch case, the cases must be constant
7. struct and union can't have static type variable
8. typedef variable can't be used inside its defination

 