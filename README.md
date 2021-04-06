# Clang--LLVM-Project
Mini Assignment 2: Large Code Bases and OOP, for the course CS2433: POPL2


#       **CS2433: POPL2**
#       ***Mini Assignment 2: Large Code Bases and OOP***
# 
### Name: Naitik Malav || Roll No.: CS19BTECH11026
# 
# Clang- LLVM Code Base
# 

#### *1. cpp11 and cpp14 features used in code are -*
- The very first thing that I have noticed is- they are using *auto* as a return type in function. I mean there's no such feature in older versions of c++ like c++11.
- Second noticable point is for lambdas. I mean they now support auto as parameters,  basically it allows a template lambda functions to be created and reused. And few more powerful capture abilities which helps programmer in OOPs. It also known as a *generic lambda*.
- Std c++ concepts like polymorphism, constructor, destructor, inheritance, classes, objects, etc are used.


#### *2. Class Hierarchy*
Class Hierarchy in LLVM project is defined as-
- **The Module class** - In this type mainly we are going to store functions, global variables and symbol tables. It's basically a top-level class in LLVM project.
- **The Function class** - It's base class is *module class*. It is used to store mainly 3 types of information which is- Basic block, symbol tables and formal arguements.
- **The BasicBlock class** - It's base class is *module class*. It is used to store mainly 3 types of information which is- Basic block, symbol tables and formal arguements.
- **The Instruction class** - It's the lowest class which forms BasicBlock class.

#### *3. OOP design decisions for LLVM and Design Patterns*

*The most important aspect of Clangs design is the LLVM Intermediate Representation (IR) which Clang's going to use to represent code in the compiler.*

Clang is based on the LLVM, and the idea behind LLVM is to use LLVM Intermediate Representation(IR). The most important aspect of LLVM design is that it is defined as a first class language with well defined semantics. It also supports lightweight runtime optimizations, whole program analysis, aggressive restructuring transformations, cross-function/interprocedural optimizations, etc. 

The most commonly used design for the designing static compilers nowadays is three phase designs. The major components of design part of this type of static compilers are 
- the front end,
- the optimiser,
- the back end (code generator)

In the starting front end parses source code and checked it for errors and basically builds a language-specific Abstract Syntax Tree (AST) to represent the input code. After that Abstract Syntax Tree is going to convert into a new representation for optimization and then the optimizer and back end will run on the code.

The main purpose of optimizer is to improve code's running time by eliminating unnecessary calculations. 

The back end is used in mapping source code into instruction set. It includes like instruction selection, register allocation, and instruction scheduling.

#### *4. Use of iterators and their own data-structures*
I noticed that using iterators we can go through LLVM data structures. We can also iterate over the operands of the instructions.

Also few more noticable points from Clang-LLVM Project:
- An iterator over a LoopInfo gives us a collection of loops.
- An iterator over a loop gives a collection of basic blocks that constitue that loop.
- An iterator over a Module gives us a list of Functions.
- An iterator over a Function gives us  a list of basic blocks.
- An iterator over a block gives us a list of instructions.

'+
