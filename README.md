# @@@@@@@@@@@@@@@@@@@@@@@@@@@ <br> THIS IS INCOMPLETE, PLEASE DO NOT GRADE THIS YET! I WILL BE SUBMITTING THIS A DAY LATE BEFORE MIDNIGHT TODAY! <br> @@@@@@@@@@@@@@@@@@@@@@@@@@@

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
<br>

## About the tools

### What is rustc?

"rustc" is the compiler for the Rust programming language, provided by the project itself. Compilers take your source code and produce binary code, either as a library or executable.

Most Rust programmers don't invoke rustc directly, but instead do it through Cargo.

**Basic Usage**

Let's say we have a 'hello class' method in a file class.rs:
```
fn main() {
    println!("Hello, class CSCI3055!");
}
```

To turn this source code into an executable, you can use rustc as follows (e.g. for windows):

	> $ rustc class.rs
	> $ .\class.exe      OR      simply $ class


Now let's look at how efficeintly this can be done using Cargo. Cargo is the Rust package manager. Cargo downloads your Rust package’s dependencies, compiles your packages and makes distributable packages.

To start a new package with Cargo:

	> $ cargo new hello_class

	> $ cd hello_class
	> $ tree .
	> .
	> ├── Cargo.toml
	> └── src
	>     └── main.rs

Cargo.tomla is the manifest, and it contains all of the metadata that Cargo needs to compile your package.

	> [package]
	> name = "hello_class"
	> version = "0.1.0"
	> authors = ["Your Name <you@example.com>"]

Let's write our 'hello class' function in main.rs,

	> src/main.rs
```
fn main() {
    println!("Hello, class CSCI3055!");
}
```
Now, we can compile and run Cargo with command,

	> $ cargo run
	>      Fresh hello_class v0.1.0 (file:///path/to/package/hello_class)
	>    Running `target/hello_world`
	> Hello, class CSCI3055!!

For information about installing Rust and Cargo package manager:  https://www.rust-lang.org/tools/install

<br>


## About the standard library

The Rust Standard Library provides the convenient high level abstractions by which a majority of Rust softwares are created with. It provides constructive features such as the Vec, Iterator, Option, Result, and String, hashmap types; a vast amount of methods for language primitives; a large number of standard macros; I/O and multithreading support; heap allocations with Box; and many more high level features.

### Vector

The first collection type we’ll look at is Vec<T>, also known as a Vector. Vector allows you to store more than one value in a *single data structure* that puts all the values next to each other in memory.

**Initializing Vectors**

To create an empty vector, we can call the Vec::new function:

`let samplevec: Vec<i32> = Vec::new();  i32 refers to the 32-bit signed integer type`

You rarely need to do this type of annotation. More commonly, you only have to create a Vec<T> that has initial values, and Rust provides the vec! macro for convinience. It will create a new vector that holds values of the type you give it. <br>
For example the exmaple below initializes a vector of 32-bit signed interger type:

`let samplevec = vec![1, 3, 5];`

**Pushing and Getting elements**

Let's see how we can add to a vector and retrieve an element at specific index,
```
let mut samplevec = vec![1, 3, 5];
samplevec.push(7);
samplevec.push(9);
samplevec.push(11);
let third = &samplevec[2];
println!("The third element is: {}", third);
```
**Iterating over Vectors**

The code shows how to use a for loop to get immutable references to each element in a vector of i32 values and print them:
```
let samplevec = vec![55, 8, 91];
for i in &samplevec {
    println!("{}", i);
}
```
If you wish to mutate these integer values instead use, 'for i in &mut v' also initialize the Vector as mutable.

### String

The String type, which is provided by Rust’s standard library rather than coded into the core language, is a growable, mutable, owned, UTF-8 encoded string type. Let's look at few examples of String type usage,
```
let mut samplestr = String::new();
let samplestr = String::from("some stuffs");
```

**Adding two strings together,**
```
let mut samplestr1 = String::from("My name is ");
let samplestr2 = "Jude";
samplestr1.push_str(samplestr2);
let samplestr3 = samplestr1 + &samplestr2;  // using concatenation with operator + also s1 cannot been used anymore
println!("samplestr1 is {}", samplestr1);
println!("samplestr3 is {}", samplestr3);
```

**Iterating over a string,**
```
for c in "simba".chars() {   // .bytes() returns each raw byte
    println!("{}", c);
}
```
The above code splits the string into characters, and you can iterate over the result in order to access each element!

### Map

The type HashMap<K, V> stores a mapping of keys of type K to values of type V. It does this via a hashing function, which determines how it places these keys and values into memory. 

**Creating a Hash Map**

You can create an empty hash map with new and add elements with insert,
```
use std::collections::HashMap;

let mut grades = HashMap::new();

scores.insert(String::from("Jude"), 85);
scores.insert(String::from("Judit"), 58)
```

**Ownership**

For types that implement the Copy trait, i.e. i32, the values are copied into the hash map. For owned values like String, the values will be moved and the hash map will be the owner of those values. E.g.
```
use std::collections::HashMap;

let field_name = String::from("Favorite color");
let field_value = String::from("Blue");

let mut map = HashMap::new();
map.insert(field_name, field_value);
```

**Accessing and Updating values in a hash map**

We can get a value out of the hash map by providing its key to the get method,
	
	Assume the code below is part of the grades code we mentioned in the beginning (uses grades HashMap)
```
let topstudent = String::from("Jude");
let grade = grades.get(&topstudent);
```

Here, grade will have the value scored by student "Jude", and the result will be Some(&85). The result is wrapped in Some because get returns an Option<&V>; if there’s no value for that key in the hash map, get will return None. The program will need to handle the Option!

We can iterate over each key/value pair in a hash map in a similar manner as we do with vectors, using a for loop:

```
for (key, value) in &grades {
    println!("{}: {}", key, value);
}
```

The following code will replace/update the value of a particular key,
```
scores.insert(String::from("Jude"), 95);
println!("{:?}", scores);
```

Vectors, strings, and hash maps will provide a large amount of functionality necessary in programs when you need to store, access, and modify data.

Let's take a look at two more librares used extensively by Rust developers for handling files,

```
use std::env;
use std::fs;

fn main() {
    let args: Vec<String> = env::args().collect();
    println!("{:?}", args);
    let filename = args;
    println!("In file {}", filename);

    let contents = fs::read_to_string(filename)
        .expect("Error! Cannot read file.");

    println!("With text:\n{}", contents);
}
```

The std::env mentioned above allows the use of command line arguments and use statement to bring in a relevant part of the standard library: we need std::fs to handle files

<br>



## About open source library

Rust lanuage is community driven and aids wide range of open source projects. Support for embedded systems is driven by a best-in-class open source community, with support from commercial partners.

Let's look at few trending open source libraries/projects developed by the community,

### ripgrep (rg)

ripgrep is a line-oriented search tool that recursively searches your current directory for a regex pattern while respecting your gitignore rules. ripgrep has first class support on Windows, macOS and Linux, with binary downloads available for every release. ripgrep is similar to other popular search tools like The Silver Searcher, ack and grep.

__source link:__  https://github.com/BurntSushi/ripgrep

### fd

fd is a simple, fast and user-friendly alternative to find.<br>
While it does not seek to mirror all of find's powerful functionality, it provides sensible (opinionated) defaults for 80% of the use cases.

**Features**
 - Convenient syntax: fd PATTERN instead of find -iname '*PATTERN*'.
 - Colorized terminal output (similar to ls) and he command name is 50% shorter* than find!
 - It's fast and has regular expressions.
 - Smart case: the search is case-insensitive by default. It switches to case-sensitive if the pattern contains an uppercase character*.
 - Ignores hidden directories and files, by default and ignores patterns from your .gitignore, by default.

__source link:__  https://github.com/sharkdp/fd

### Yew

Yew is a modern Rust framework inspired by Elm and ReactJS for creating multi-threaded frontend apps with WebAssembly.
The framework supports multi-threading & concurrency out of the box. It uses Web Workers API to spawn actors (agents) in separate threads and uses a local scheduler attached to a thread for concurrent tasks.

__source link:__  https://github.com/DenisKolodin/yew

<br>


<br>



# Analysis of the language

The following questions and answers will carefully identify and assist you in comprehending the language, and to assess if it fits your programming criteria,

1. *What is the style of programming supported by the language: functional vs procedural programming?*

> Rust is a systems programming language supporting both functional and imperative (continuations, do notation for state monads) paradigms. Most of the core design tenants are derived from functional paradigms, including, but not limited to pattern matching, immutability, closures, algebraic data types etc... They have taken some aspects of object orientation (i.e. self) to allow for nice encapsulation. In the end it's the best of both worlds (Imperative & Functional).

2. *How is its ability to perform meta-programming such as macros?*

> Macros are code that manipulates code. Rust supports extensive metaprogramming via macros. 
Macros open the door to reaching some goals that are acclaimed to the Rustic way of programming:

> - Constructing redundant or insignificant code instead of letting the developer write it by hand.
> - Extending the language, for experimenting before new syntax is added properly, or filling gaps in the language.
> - Optimizing performance, by doing at compile-time what could be done at run-time.

> To reach these goals, Rust includes two types of macros, function-like and attribute-like.

3. *Provide details of symbol resolution and its support for closure?*

>

4. *Give example of scoping rules supported by the language: lexical vs dynamic scoping?*


5. *Explain functional programming constructs either as part of Rust or supported by the standard library of the runtime?*
> Rust’s design is heavily influenced by existing languages and techniques, and one eminent influence is "functional programming". Programming in a functional style often includes using functions as values by passing them in arguments, returning them from other functions, assigning them to variables for later execution, and so forth. Few examples of functional constructs in Rust are,
> - closures: a function-like construct you can store in a variable, `example_closure = |x| x;`
> - iterators: a way of processing a series of elements, `samplevector.iter()`
> - pattern matching: match against literals directly using arms
> - enum:  allows the creation of a type which may be one of a few different variants

6. *What is the type system of Rust: static vs dynamic types?*
> Rust is static type intensive language where you cannot add or remove objects at runtime. For example, a predefined struct is a static data structure, as we cannot add or remove keys at runtime. Therefore making it more secure in preserving anonymity and protecting data.
`let x = vec![1,2,3,4];` is 'static, but `let x = vec![&1,&2,&3,&4]` isn't, since the latter is a `Vec<&'a int>`

7. *What are some of the strengths and weaknesses of the language?*
> Rust is a great language because it is a systems language in that it gives you the level of flexibility and control you get with a language like C or C++, but at the same time it is safe by default (immense security). It has a good type system, and a powerful concept around memory management: no memory leak nor null pointer exception and db connections!

> However, Rust is a bit harder to learn (although its syntax is relatively simple), has different concepts that must sink in your mind before becoming proficient.  Rust is very explicit, as it throws a lot of wrenches in their path, ownership/borrowing, failures that must be dealt with immediately (rather than exceptions that can be ignored). Also, it currently doesn’t have a lot of open source libs in comparison to other large scale langaues such as Java and C++. Overall, rust is somewhat unfriendly to beginners, however if you put the time and effort, its performance and reliability will soon grow on you!


