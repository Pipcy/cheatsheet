# C Cheatsheet for Programmers

This cheat sheet covers basic C concepts.

## Basic Structures
```C
main()
{
  printf(“\n Hello World! \n”);   // stuff here is a comment
                                // The \n means CR&LF
}
```
Declare variables
```C
int var_a;
int var_b, var_c; /* combined */
int step = 20; /* with init */
```
Declare arrays
```C
int nums[10];
int nums[10][10];
int i, num[10], j, myftn(); // combine declaration legal
```
## Data Types
`char` -- byte (used mostly for characters and Booleans)

`unsigned char` -- unsigned byte

`short int` -- halfword (2 bytes)

`unsigned short int` -- unsigned halfword

`int` -- one word (4 bytes)

`unsigned int` -- unsigned word

`long int` -- double word (8 bytes)

`unsigned long int` -- unsigned double word

`float` -- single precision floating point (4 bytes)

`double` -- double precision floating point (8 bytes)

## Arithmetic & Bitwise Operators
arithmetic operators `+` `-` `*` `/` `%` `-(negative)`

BIT-WISE two operand `|` OR `&` AND `^` XOR -- only works for integer types (int, char etc.)

BIT-WISE single operand `~` NOT
```C
(1010 & 1100) == 1000
~1010 == 0101
```

shift operators `<<` shift left, `>>` shift right
```C
(1010 << 1) == 10100 // one extra space
(1010 >> 1) == 101 // fall off
```

LOGICAL two operand `&&` AND `||` OR

LOGICAL single operand `!` NOT

### bit-wise vs. Logical operations
```C
int a = 1, b = 2;
if (a) //true
if (b) //true
if (a && b) //true && true = true
if (a & b) //false 01 & 10 ==
if (!b) // false
if (~b) // false
```
### increment & decrement
prefix vs postfix
```C
a = 10;
b = ++a; // after this point, a == 11, b == 11

a = 10;
b = a++; // after this point, a == 11, b == 10 - assign the old a to b, then increment
```

## Conditional Expression
### If/Else
```C
if (condition1)
  statement1;
else if (condition2){
  statement2;
  statement; }
else{
  statement4; }
```
### Switch
```C
switch (date_in_march) {     // evaluate expression – execute
                            // statement following case if
                            // val# == expr is TRUE
case 1: …;
break;                      // no break means continue on to next
case 2: …;
break;
…
case 31: …;
break;
default: …;                 /* optional, e.g. handle error */
}
```
### While
```C
while (i <= exp) {
res *= base;
i++; }
```
do while loop
```C
do
…
while (expr);
```

### For Loops
```C
for (res = 1; exp > 0; exp--)
  res *= base;                    // res = res * base;
                                  // can also do += /= -= etc.
for (i = 0; i < count; i++) {
                                  // do this stuff count times
                                  // (unless you modify i in
                                  // here, which is legal but
                                  // very bad programming
                                  // practice!!)
  …
}
```

### loop examples
```C
main()
{
int input[5] = {32,100,10,20,50};
int output[5], count = 5, i;
for (i = 0; i < count; i++)
  if (input[i] >= 0)
    output[i] = (input[i] * 9) / 5 + 32;
}
```

## Strings
C does not have built-in strings, `char s[] = “Hello”;` is shorthand for `char s[6] = {‘H’, ‘e’, ‘l’, ‘l’, ‘o’, ‘\0’};`

## Addresses and Pointers
`&` address of
`*` content of
```C
int c = 1;
int *p;     // pointer declaration
            // (will point to an int)
p = &c;     // & op applied to a var
            // evals to its address;
            // p is now set to
            // address of c
```
Another example
```C
int x = 1, y = 2, z[10]; // declarations
int *ip;                 // declare variable to be used as pointer
ip = &x;                 // ip points to (has address of) x
y = *ip;                 // y set to value of ip’s referent x,
// i.e. to 1
*ip = 0;                 // ip’s referent, x, set to 0
ip = &z[0];              // ip now points to z[0]

                         // after execution, x == 0, y == 1;
```
### pointers and arrays
int a[6] = {0,10,20,30,40,50};
• `a[0]` returns an `int`
• `&a[0]` returns the address of that `int`
• `a` returns the same address as `&a[0]`

example
```C
int a[6] = {0,10,20,30,40,50};
int *ip;
ip = &a[0];
printf(“%d %d %d %d %d %d %d”,
a[0], *ip, *(ip+1), *ip++, *ip, *(ip+3), *(ip-1));  // "*(  )" dereference, get the content 

//output:
0
0
10
0 // "*" deference ip which is pointing at 1st element, then post increment ip, then ip points to 10
10
40
0
```
#### Pointer Usage
```C
int A[100], B[100];
int *pA, *pB;

//version 1
for (i = 0; i < 100; i++) A[i] = B[i]; // no pointers

//version 2
pA = A; pB = B;                        //A is an address
for (i = 0; i < 100; i++) *pA++ = *pB++; // pointers, more efficient
```

## Memory Allocation
### Stack - LIFO

### Heap - FIFO
- dynamically allocate
- must be freed using `free`
