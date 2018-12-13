
Few examples of basic syntaxes used in main.md file from home page (Please refer to it for details!)


## Declaring Variables, Tuples and Mutability

```
let a = 10;

let a: int = 10;

let mut a: int = 10;
a = 20

let tuple = ("My tuple", -1, 4.20, true); 

```

## Conditionals and Print Statement

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

## Pattern Matching

```
match isEven(i) {
	true => println!("This is an even value!"), // use comma to seperate
	false => println!("This is an odd value!")
}
```

## Looping (while, loop, for)

```
let mut a = 0;
while i < 5 { 
	println!(i);
	i += 1; // Rust doesn't support ++ or --
}

loop {
	//code
}

for i in range(0, 5) {
	square(i);
}
```

## Expressions

```
let a = if x == 5 {
                "apples"
        }
        else {
                "oranges"
        }
        
        
let x = match y {
    0..9    =>  { "Less than 10" }  // 0..9 refers to values from 0 to 9 (these are called arms)
    _       =>  { "Greater than 10" }  // default arm
}
```

## Fuctions

```
fn sayHello() {
	println!("hello!");
}

fn addTen(i: int) -> int {
	i+5
}

fn main() {
	fn theatre() { println!("Cineplex"); }
	theatre();
}
```
