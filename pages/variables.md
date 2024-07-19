# Variables

## Summary
0. [Summary](#summary)
1. [Variables location](#location)
1. [Variables types](#types)
2. [Appendix: Spill on the stack](#stack-spilling)

# Location

Since jasmin is a low-level language, you can actually choose where your variables will be placed. There are three possibilites:
 - **`inline`**: A variable annotated `inline` won't appear after compilation: during linkage the compiler will compute all the necessary values and put them directly in the code
 - **`register`**: The variables annotated `reg` are stored in register. Please note that your computer only has a limited number of register, and therefore stack spilling (which will be discussed later) is sometimes necessary
 - **`stack`**: The variables annotated `stack` are stored in the stack.

# Types
 - **`int`** is a variable contaning an int
 - **`uX`** where `X` is an integer in the set {8, 16, 32, 64, 128, 256} denotes a X-bits  variable
# Stack Spilling

> [!TIP] 
> You can sometimes avoid the error
> > compilation error:  
> > register allocation: cannot allocate x.447 into RAX.66, the variable is already allocated in RDI.59  
> > make: *** [alzette.s] Error 1  

> whithout using stack spilling; in order to do so, simply use `x=x` or `x=#LEA(x)` at the right place in your code

Due to the limited number of register in your computer, you may use all of those when using `reg` annotation.  
A simple way to do this is by using [`stack spilling`](https://en.wikipedia.org/wiki/Register_allocation) when necessary, which basically means to store a variable in memory when you don't use it in order to free the associated register.  
Stack spilling in Jasmin can be done this way:
```
reg x;         // the variable to be spilled
stack x_stack; // a save in memory
[code]
x_stack = x;   // spilling the variable onto the stack
[code]         // code using the freed register
x = x_stack;   // restoring variable
[code]
```
