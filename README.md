# @@@@@@@@@@@@@@@@@@@@@@@@@@@ <br> THIS IS INCOMPLETE, PLEASE DO NOT MARK THIS! I WILL BE SUBMITTING THIS A DAY LATE BEFORE MIDNIGHT TODAY! <br> @@@@@@@@@@@@@@@@@@@@@@@@@@@

# CSCI3055U Final Project on Rust Language

- _Jude Antonyrajan_
- _jude.antonyrajan@uoit.net_

## Introduction

> Welcome to the guide about Rust Programming Language. Rust can be better identified as a system programming language that focuses mainly on rapidity, concurrency and security and upholding pure-function, imperative-procedural and object oreinted style. Rust intends to be higly reliable, concurrent, secure and overall extremely efficient.
This has led to the thorough development and progression on these fields and particularly on control on memory layout. 
Performance of Rust is oftentimes compared to that of C-family languages.


## History

> Rust is fairly a new language relative to its predecessors, e.g. C, which preceded it by 38 years. Rust is considered to be a breed of C-like language, but with advanced features which creates significant advantages over its ancestors.
Notably, Rust is heavily inspired by Cyclone (a safe dialect of C and a fundamental language), with some aspects of object-oriented features from C++. But, it also includes functional features from languages like Haskell and OCaml. The result is a C-like language that supports multiparadigm programming (imperative, functional, and object oriented). Rust is sponsored by Mozilla Research.


## Some interesting features:
> - It's the holy grail of memory management
> - Avoids garbage collecting, refcounting, and manual memory management
> - Immutable by default, no global variables, private by default, and so on...

## About the syntax

Now, let's go over some basic syntax of Rust. We'll learn about variable declarations and mutability, how to work with functions, and some basic control structures including loops, conditionals, and matching.

### Variables

**Declaration and Typing:**

*Here is a valid variable declaration in Rust:*

```
let a = 10;
```
You've probably noticed that there is no explicit statement of type here; instead, the compiler infers that variable 'a' should &emsp;be an int. Rust's compiler is typically very good at correctly inferring types for variables.

However there are times when the compiler draws incorrect conclusion, we can explicitly tell the compiler what we want this type to be to fix this.
```
let a: int = 10;
```

**Mutability:**

All Rust local variables are, by default, Immutable - meaning that you cannot change their assigned value once given (Final). In order to make a mutable local variable, you must introduce the keyword - __mut__ :
```
let mut a: int = 10;
a = 20
```

**Tuples:**

Rust features an additional type named a tuple. Tuples are groupings of values, similar in appearance 
but different in &emsp;function to a list of variables.

One nice feature is that tuples are heterogeneous; we can mix field types similar to python lists. <br>
__Note:__ Tuple elements are immutable, and its fields can't be accessed directly. Also a tuple cannot be empty!
```
let tuple = ("My tuple", -1, 4.20, true); 
```


### Conditionals and Print Statement


Rust’s conditionals and print statement are are almost identical to what we've seen in Java or another C type language
(println without the need of "system.out" in Java + ! symbol) . The associated keywords are if , else if , and else , and are followed by a boolean expression and conditional block.

```
if a == 10 { 
    println!("The integer value is 10"); 
}
else if a == 5 { 
    println!("The integer value is 5");
}
else { 
    println!("It's neither 10 or 5"); 
}
```

### Pattern Matching

Instead of using a “switch” statement widely used in many languages, Rust uses the match statement. Match is much efficient and reliable than switch statement, and is used fairly extensively in a lot of Rust code.

```
match isEven(i) {
	true => println!("This is an even value!"), // use comma to seperate
	false => println!("This is an odd value!")
}
```

### Looping

Rust provides several choices of looping structure, similar to those in C and Java.

**while:**
```
let mut a = 0;
while i < 5 { 
	println!(i);
	i += 1; // Rust doesn't support ++ or --
}
```
**loop:**

Loop is syntactic for while true .
```
loop {
	//code
}
```
**for:**

Rust’s for loop is more similar to python’s for-each loop than to a traditional for loop. It uses an iterator to loop over the values in a range of numbers.
```
for i in range(0, 5) {
	square(i);
}
```

### Expressions

Almost everything in Rust can be an expression; the only exceptions are declarations. This allows Rust code to be brief and concise. For example, a return from a function is not necessary in most cases, wherease return keyword is only used when you want to leave a function early. 
Another common use of Rust's expressions is easy conditional assignment of variables, as a conditional block will have the value of its last expression:

```
let a = if x == 5 {
                "apples"
        }
        else {
                "oranges"
        }
```

```
let x = match y {
    0..9    =>  { "Less than 10" }  // 0..9 refers to values from 0 to 9 (these are called arms)
    _       =>  { "Greater than 10" }  // default arm
}
```

### Functions

Functions are created by using __fn__. Here’s the syntax for a function that accepts no parameters and only prints a string:
```
fn sayHello() {
	println!("hello!");
}
```

A return value is specified using -> type after the parameter list. To actually return a value, we use Rust's expressions.
```
fn addTen(i: int) -> int {
	i+5
}
```

Unlike many other languages, functions can be declared within another function in Rust:
```
fn main() {
	fn theatre() { println!("Cineplex"); }
	theatre();
}
```

## About the tools

> _Describe the compiler or interpreter needed_.

## About the standard library

> _Give some examples of the functions and data structures
> offered by the standard library_.

## About open source library

> _Describe at least one contribution by the open source
community written in the language._

# Analysis of the language

> _Organize your report according to the project description
document_.


