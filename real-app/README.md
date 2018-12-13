
### CSCI 3055U - Programming Languages - Real-App

## Newton's method for solving roots of polynomials

In this real-application, we will be programming in Rust and experiment with the basics of functional programming. We will be implementing the Newton's method for solving roots of polynomials which we completed in Assignment 1 using Python & Clojure languages. *(ax^3+bx^2+cx+d=0)*


__Given data:__

|  Polynomial   |     Value     |
| ------------- | ------------- |
|       a       |      1.0      |
|       b       |      0.0      |
|       c       |     -1.0      |
|       d       |      1.0      |

  

```
// global struct
static POLYNOMIAL_VALUES: MyStruct = MyStruct {
    a: 1.0,
    b: 0.0,
    c: -1.0,
    d: 1.0,
};

// computes polynomial for the given static values
// return a*x*x*x + b*x*x + c*x + d

fn f(x: f32) -> f32 {

    return POLYNOMIAL_VALUES.a*x.powf(3.0)
     + POLYNOMIAL_VALUES.b*x.powf(2.0)
     + POLYNOMIAL_VALUES.c*x
     + POLYNOMIAL_VALUES.d;
}

// computes derivative
// return 3*a*x*x + 2*b*x + c  (equivalent to: 1st derivative of fx = f'x)

fn dfx(x: f32) -> f32 {

    return 3.0*POLYNOMIAL_VALUES.a*x.powf(2.0)
     + 2.0*POLYNOMIAL_VALUES.b*x
     + POLYNOMIAL_VALUES.c;
}

// performs newton's method for solving roots of polynomial

fn newton_solver(mut x0: f32, n: i32) -> f32 {
    // same as range(0, n) in python
    for i in 0..n {
        x0 = x0 - f(x0)/dfx(x0);
    }
    return x0;
}

// main function to test the implementation for n=10

fn main() {
    let x = newton_solver(0.0, 10);
    let y = f(x);   // same as a*x*x*x + b*x*x + c*x + d
    println!("for n = 10 : x = {:.8}, y = {:.8}", x, y);   //std::fmt
}

// initialize values with their corresponding type

struct MyStruct {
    a: f32,
    b: f32,
    c: f32,
    d: f32,
}
```

  > for n = 10 : x = 0.40494919, y = 0.66145593
