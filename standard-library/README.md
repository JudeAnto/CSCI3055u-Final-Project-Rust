
Few examples of standard library functionalities (Refer to readme.md file from homepage for vivid explanation!)

## Vector - declare, push, retrieve, iterate

```
let samplevec: Vec<i32> = Vec::new(); i32 refers to the 32-bit signed integer type

let samplevec = vec![1, 3, 5];


let mut samplevec = vec![1, 3, 5];
samplevec.push(7);
samplevec.push(9);
samplevec.push(11);
let third = &samplevec[2];
println!("The third element is: {}", third);


let samplevec = vec![55, 8, 91];
for i in &samplevec {
    println!("{}", i);
}
```

## String - Add/concatenate, iterate

```
let mut samplestr = String::new();
let samplestr = String::from("some stuffs");


let mut samplestr1 = String::from("My name is ");
let samplestr2 = "Jude";
samplestr1.push_str(samplestr2);
let samplestr3 = samplestr1 + &samplestr2;  // using concatenation with operator + also s1 cannot been used anymore
println!("samplestr1 is {}", samplestr1);
println!("samplestr3 is {}", samplestr3);


for c in "simba".chars() {   // .bytes() returns each raw byte
    println!("{}", c);
}
```

## Map - creation of HashMap, ownership, accessing & updating

```
use std::collections::HashMap;

let mut grades = HashMap::new();

scores.insert(String::from("Jude"), 85);
scores.insert(String::from("Judit"), 58);



let fkey = String::from("Best Film");
let fvalue = String::from("Intestellar");

let mut map = HashMap::new();
map.insert(fkey, fvalue);



let topstudent = String::from("Jude");
let grade = grades.get(&topstudent);


for (key, value) in &grades {
    println!("{}: {}", key, value);
}


grades.insert(String::from("Jude"), 95);
println!("{:?}", grades);



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
