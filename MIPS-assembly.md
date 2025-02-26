## MIPS Assembly

### Basic
exit program
```
end:
    li $v0, 10        # Exit program
    syscall
```

### Printing

print string
```asm
li $v0, 4       
la $a0, str     # str is the variable name of the string to print
syscall
```

print integer
```asm
li $v0, 1           # system call for print int
move $a0, $t1       # set up int to print (or li $a0, 5 for a immediate)
syscall
```

### Arithmetic Core Instruction Set
```
div $t1, $t0     # t1 / t0
mfhi $t2         # store remainder
mflo $t3         # store quotient
```

```
bclt
bclf

divu
add s
add d
c.x.s*
c.x.d*
div s
div d
mul s
mul d
sub s
sub d
lwcl
ldcl

mfc0
mult
multu
sra
swcl
sdcl
```

