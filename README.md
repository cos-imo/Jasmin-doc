<img src="https://github.com/cos-imo/Jasmin-doc/blob/main/ressources/images/jasmin.png" width="64" align="left" />

# Jasmin documentation

## Table of contents

0. [Table  of contents](#table-of-contents)
1. [About Jasmin](#about-jasmin)
2. [Installation](#installation)
3. [Pages](#pages)


## About Jasmin
> [!Warning]
> This text is just a copy-paste about the "About" section of the official wiki   
> You can access it directly [here](https://github.com/jasmin-lang/jasmin/wiki/About)   
Jasmin is a workbench for high-assurance and high-speed cryptography. Jasmin implementations aim at being efficient, safe, correct, and secure.

The Jasmin **programming language** smoothly combines high-level and low-level constructs, so as to support “assembly in the head” programming. Programmers can control many low-level details that are performance-critical: instruction selection and scheduling, what registers to spill and when, etc. They can also rely on high-level abstractions (variables, functions, arrays, loops, etc.) to structure their code and make it more amenable to formal verification.

The **semantics** is formally defined to allow rigorous reasoning about program behaviors. The Coq definitions can be found in the `proofs/lang/sem.v file. This semantics is executable, thus Jasmin programs can be directly [interpreted](https://github.com/jasmin-lang/jasmin/wiki/Reference-interpreter).

Jasmin programs can be automatically checked for **safety** and **termination** (using a trusted [static analyzer](https://github.com/jasmin-lang/jasmin/wiki/Safety-checker)).

The Jasmin compiler produces predictable assembly and ensures that the use of high-level abstractions incurs no run-time penalty. It is formally verified for correctness (the precise Coq statement and the corresponding machine-checked proofs can be found in the `proofs/compiler/compiler_proof.v file). This justifies that many properties can be proved on a source program and still apply to the corresponding assembly program: safety, termination, functional correctness…

The Jasmin workbench leverages the [EasyCrypt](https://www.easycrypt.info) toolset for **formal verification**. Jasmin programs can be [extracted](https://github.com/jasmin-lang/jasmin/wiki/Extraction-to-EasyCrypt) to corresponding EasyCrypt programs to prove functional correctness, cryptographic security, or security against side-channel attacks (constant-time).

## Installation
> [!Warning]
> Those are just two commands you can use to  install Jasmin
> Please consult the [official wiki](https://github.com/jasmin-lang/jasmin/wiki/Installation-instructions) for extensive information

**Using nix shell**
```
nix-env -iA nixpkgs.jasmin-compiler
```
**Using opam**
```
run opam install jasmin
```

## Pages
The following pages are available in this documentation:
 - [Basic Jasmin usage](https://github.com/cos-imo/Jasmin-doc/blob/main/pages/basic-usage.md)
 - [Functions](https://github.com/cos-imo/Jasmin-doc/blob/main/pages/functions.md)
 - [Annotations, types and variables](https://github.com/cos-imo/Jasmin-doc/blob/main/pages/annotations-types-and-variables.md)
 
