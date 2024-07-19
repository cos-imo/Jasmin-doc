# Functions

> [!TIP]
> To make sure you understand the point of `export` functions, make sure to read the [basic usage](https://github.com/cos-imo/Jasmin-doc/blob/main/pages/basic-usage.md) page, or even better, [the official wiki](https://github.com/jasmin-lang/jasmin/wiki)

## Summary
0. [Summary](#summary)
1. [Basic function definition](#basic-function-definition)

# Basic function definition

A function in Jasmin looks like

```
[annotation]
fn function_name(parameters) -> res {
[function code]
}
```

where the prefix **`annotation`** can be nothing, `export` or `inline`, **`parameters`** is a list of the function parameters, and **`res`** is the type of the return  value, is the function has any.  
Please consult [annotations, types and variables](https://github.com/cos-imo/Jasmin-doc/blob/main/pages/annotations-types-and-variables.md) for more  informations.

Functions that are not marked with inline or export are local functions: they will be preserved by the compiler but are not visible from the outside (i.e, they cannot be called from non-Jasmin code).
