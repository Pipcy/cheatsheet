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
