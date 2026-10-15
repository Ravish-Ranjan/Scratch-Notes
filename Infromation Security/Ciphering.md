# Ciphering

1. Additive cipher
2. data in message is offseted by key amount cyclical

```
message : "bombardilo crocodilo" 
key : 3 offsetting all chars by 3 position 
codeword : "erpecuglor furfrglor" 
```

2. Prime number properties
  1. infinitly many prime numbers : mmultiplying multiple prime no.s from start to some and adding 1 gives no. which is not divisible by any of the multiplying prims.
  2. eg (2*3*5) + 1 = 31 -> not divisible by 2 or 3 or 5
  3. Every integer can be writen in form

$$
6k + i \newline i \in \text{{-1,0,1,2,3,4}}
$$

2. for every prime greater than 3 has to be in form 6k + 1 or 6k - 1
3. if an integer N has no divisor of the form 6k+1 or 6k-1 up to root of N then N is prime provided that it is not divisible by 2 or 3
  1. Wilson theorem :

$$
(p-1)! = -1 (mod p) \newline \text{where p is a prime no.}
$$

5. Fermat's little theorem : $$ a^{p-1} = 1 (modp) \newline 1 < a < p \newline gcd(a,p) = 1 $$
6. pseudoprime : which make fermat's test fail
7. Miller-rabin test : $$ N-1=2^s d \newline d = odd $$
8. Congruence

$$
a = b(mod n)
$$

a is congruent to b if by dividing a by n gives remainder b 
2. a = b(modn) => b = a(modn) 

```
a = b(mod n) b = c(mod n) 
to prove 
a = c(mod n) 
a = b + nk 
b = c + nj 
a = c + nj + nk 
a = c + (j+k)n 
a = c(mod n) 
```

3. a = b(mod n) ,c = d(mod n)
4. a+c = b+d (mod n)
5. a-c = b-d (mod n)
6. ac = bd mod(n)
7. ax = bx mod(n) => a = b (mod n) if gcd(x,n) = 1

```
5x + 6 = 13 (mod 11)
5x = 7 (mod 11)
5x = 40 (mod 11)
x = 8 (mod 11)
```

8. multiplicative inverse
  1. for a equation 5x = 7(mod 11)
  2. multiplicative inverse of 5 (mod 11) is z where 5z = 1 (mod 11)
  3. there for at z = 9 5z = 45 and 45 %11 = 1 therefor 9 is multiplicative inverse of 5 in 5 (mod11)
  4. we can multiply by multiplicative inverse on both size of equation
  5. 9*5x = 9*7 (mod 11) = > x = 63 (mod 11)
9. solve for 1111x = 4 (mod 12313)
  1. it is hard to find multiplicative inerse of 1111z = 1(mod 12313)
  2. use gcd aka hcf
10. Eculidean algorithm
  1. gcd(a,b) = gcd(b,a%b)    gcd here will be last non-zero remainder of a%b
11. Extended euclidean algorithmcodeword
  1. gcd(a,b) = ax + by   where x ,y is multiplcative inverse of a,b repectivly

```
extended euclidean on 35,12
35 = 12 * 2 + 11
12 = 11 * 1 + 1
11 = 1 * 11 + 0

gcd = 1

reverse (remainder = divident - divisor * quotient)
1 = 12 - 11 * 1
11 = 35 - 12 * 2

substituting value of 11
1 = 12 - (35 - 12 * 2) * 1
1 = 12 - 35 + 24
1 = -35 + 12 * 3
gcd(35,12) = (-1) * 35 + 3 * 12
x = -1
y = 3
```

12. Affine cipher
  1. E(x) = (ax + b) mod 26
    1. x is the numerical equivalent of character
    2. a,b are integers
    3. gcd(a,26) = 1
  2. y = (ax + b) %26
  3. y-b = ax % 26
  4. ax = y-b  % 26
  5. E^-1(x) = a^-1 (y-b) % 26    where a^-1 is multiplicative inverse of 5 mod 26 or 5z = 1 mod 26

```
do affine cipher of "ITS COOL" with E(x) = (5x + 8) mod 26
plains   I  T  S  C  O  O  L
x        8 19 18  2 14 14 11
E(x)    22 25 20 18  0  0 11
Message  W  Z  U  S  A  A  L
```

 