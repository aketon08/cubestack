# Cubestack Documentation

## Contents
  - [Literals](#literals)
  - [Math](#math)
  - [Logic](#logic)
  - [List Operations](#list-operations)
  - [Other Functions](#other-functions)
  - [Conditionals](#conditionals)
  - [For Loops](#for-loops)
  - [While Loops](#while-loops)
  - [A Final Note](#a-final-note)

## Literals
Unlike sensible languages, literals are econded in base 36, then each digit is mapped to a move on a Rubiks Cube. Luckily, there is a converter on the online interpreter. 

For strings, `"hi"` would first become it's ASCII codes, `[104, 105]`, then in base 36, `["2w", "2x"]`, then each of those digits mapped to a move and enclosed in `S` and `S'`, `S R2 B2 R2 b S'`.

For numbers, the number is just converted to base 36 then has the decimal place (if present) replaced with `M2`. For example `12.34` would become `["c", "y"]`, then each digit mapped to a move, joined with `M2`, and put inside `M` and `M'` resulting in `M U M2 b' M'`. Note that to make a negative number you need to either multiply it by -1 (`M M'`) or subtract it from zero.

Lists are notated with `E` and `E'` (the equivelent of `[` and `]`) and `E2` for seperating list items. Note that until v1.1 (hopefully) literal multi-dimenstional lists will be flattened.

## Math
`R` - Add  
`R'` - Subtract (or if one of the arguments is a string and the other is a number, `str.slice(0, -num)`  
`L` - Multiply (or in the same scenario as above, `str.repeat(num)`)  
`L'` - Divide (or if one of the arguments is a string, the string reversed)  
`L2` - Exponent (or if one of the arguments is a string, `str.toUpperCase()`)  
`R2` - Nth Root (or if one of the arguments is a string, `str.toLowerCase()`)  
`U` - Modulo  

## Logic
`D` - Equal  
`D'` - Not equal  
`F` - Greater than  
`F'` - Less than  
`B` - Greater than or equal to  
`B'` - Less than or equal to  
`D2` - And  
`F2` - Or  
`B2` - Not  

## List Operations
`r` - Item at index `b` in `a`  
`r'` - Index of `b` in `a`  
`r2` - Push `b` to `a`  
`d` - Remove item at index  
`u` - Join list `a` with list `b`  
`u'` - Split list `a` at `b`  
`l2` - `a.slice(b, c)`  
`u2` - Shift list `a`, `b` times  


## Other Functions
`b` - Print  
`b'` - Get all inputs wrapped in a list  
`b2` - Push a copy of the stack to the stack  
`d'` - set the stack to the top item on the stack  
`U'` - Pop the stack  
`l'` - Swap the top two items on the stack  
`f2` - Exit the program  
`l` - Length of `a`  
`f` - Floor the top item on the stack  
`d2` - Push a random float to the stack  
`U2` - Range from `a` to `b` with a step of `c`  
`f'` - convert `a` to data type `b` (`"list"`, `number`, `int`, `float`)  

## Conditionals
Conditionals are written as `x <conditional code> x2 <optional conditional code> x'`. If the top item on the stack in truthy, the first block of code will run, otherwise, the second block of code will run.

## For Loops
For loops are created by pushing something to iterate to the stack, then pushing the name of your loop variable (as a string) to the stack. You can then use the enclose the code you want to loop in `y` and `y'`. To get the value of the loop variable, push it's name to the stack, then use the `y2` command. To break the loop, use `S2`.

## While Loops
To create a while loop, use `z <condition> z2 <code> z'`, The code will run until the condition is false. Exiting the loop is the same as exiting a for loop - `S2`.

## A Final Note

Why on earth are you here.