# Annotations, types and variables

## Summary
0. [Summary](#summary)
1. [Annotation](#annotation)
2. [Types](#types)
3. [Variables](#variables)

# Annotation

Since jasmin is a low-level language, you can actually choose where your variables will be placed. There are three possibilites:
 - **`inline`**: A variable annotated `inline` won't appear after compilation: during linkage the compiler will compute all the necessary values and put them directly in the code
 - **`register`**: The variables annotated `reg` are stored in register. Please note that your computer only has a limited number of register, and therefore stack spilling (which will be discussed later) is sometimes necessary
 - **`stack`**: The variables annotated `stack` are stored in the stack.

# Types
 - **`int`** is a variable contaning an int
 - **`uX`** where `X` is an integer in the set {8, 16, 32, 64, 128, 256} denotes a X-bits  variable

# Variables
#### Scalar variables
A variable is declared as follows:
```
<annotation> <type> var_name;
```
For instance:
```
inline int i;
stack u256 my_stack_var;
reg u8 my_reg_var;
```

> [!Warning]
> Note that inline variables will be replaced during compilation. Therefore, they can't be used as return values

#### Arrays variable
An array variable  is declared as follows:
```
<annotation> <type>[size] name;
```

For example:
```
inline u8[2] an_inline_tab;
reg u32[4] a_reg_array;
stack u64[1] a_stack_array;
```
