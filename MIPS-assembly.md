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
move $a0, $t1       # set up int to print 
syscall
```
