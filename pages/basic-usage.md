# Basic Usage
> ℹ️ **About**  
> This page is explaining the basic uses of jasmin: how to compile to assembly, how to use CLI...
> Please note that the offered content is just notes from [the official wiki](https://github.com/jasmin-lang/jasmin/wiki)

## Summary
0. [Summary](#summary)
1. [The philosophy behind Jasmin](#how-to-use-jasmin)
1. [Basic command line usage](#basic-command-line-usage)
2. [Compilation to assembly](#compile-to-assembly)

## How to use Jasmin

> [!WARNING]
> This section only covers the basic use of Jasmin: compiling code and somehow using it.  
> For more informations (e.g. using EasyCrypt) please refer to [the official wiki](https://github.com/jasmin-lang/jasmin/wiki)

Thus you can [interpret it](https://github.com/jasmin-lang/jasmin/wiki/Reference-interpreter), Jasmin is usually compiled to a shared object format (`.so`library) then called from third-party code.  
### In Python
In python, the [ctypes library](https://docs.python.org/3/library/ctypes.html) can be used to interact with `.so` files.  
Once imported:
```
import ctypes
```
You can then load libraries using `ctypes.cdll.LoadLibrary()`:
```
my_library = ctypes.cdll.LoadLibrary("path/to/your/so/file")
```
And from there you can access your function `my_function` has an attribute
```
my_fun = my_library.my_function
```
or, using `getattr`:
```
my_fun = getattr(my_library, my_function)
```
From there, you can set the types of the arguments/result value of your function:
```
my_library.my_function.argtypes = your_argtypes
my_library.my_function.restype = your_restype
```
Consult the [types offered by ctypes](https://docs.python.org/3/library/ctypes.html#fundamental-data-types) to see how you can set that up

You can then simply call the function:
```
my_result = my_library.my_function(my_args)
```

All these commands can be found in the [example script](https://github.com/cos-imo/Jasmin-doc/ressources/scripts/python_binding.py)

### In C
Not covered yet
### In assembly
Not covered yet


## Basic command line usage

**From the [official wiki](https://github.com/jasmin-lang/jasmin/wiki/Compilation-to-assembly)**

The `jasminc` program takes as argument (on the command line) the name of a Jasmin source file to compile. The default behavior is to discard the result of the compilation.

When the `-pasm` command-line flag is given, the generated assembly code is printed to the standard output.

When the `-o asmFileName` option is given (where asmFileName is a valid file name of your choice), the generated assembly is written to that file.

The assembly program is ready to be consumed by common assemblers, such as the GNU assembler.


## Compile to assembly

#### Basic compilation to assembly
```
jasminc -pasm source.jazz
```


#### Save the output in a file
```
jasminc -o target.s source.jazz
```
#### Check the safety of your program
```
jasminc -checksafety source.jazz
```
