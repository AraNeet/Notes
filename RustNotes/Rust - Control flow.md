## IF statements
- Like in every languages there are the `if` statement
``` rust
let temperature = 8;

if temperature <= 10 {
    println!("The weather is cold");
}

// Outputs: "The weather is cold"
```
- `if` Can only be bools statements. If not you'll get a compile error.
``` rust
let temperature = 8;

// This would error! Expected `bool`, found integer
// if temperature { 
//     println!("the weather is cold");
// }
```

- You can do `if else` statement for mutliple conditions
``` rust
let temperature = 15;

if temperature <= 10 {
    println!("The weather is cold");
} else if temperature <= 20 {
    println!("The weather is cool");
} else {
    println!("The weather is warm");
}


// Outputs: "The weather is cool"
```
- you can make variables be equal to the statement result
``` rust
let temperature = 15;

let weather = if temperature <= 10 {
    "cold"
} else if temperature <= 20 {
    "cool"
} else {
    "warm"
};

println!("The weather is {}", weather); // "The weather is cool"
```
- If the statement value is not only one type it will error.
``` rust
let flag = false;

// This would error!
// let six = if flag { 6 } else { "six" };
```

## Looping
- In rust there are 3 type of loops `for`, `while`, and `loop`
- `loop` is a infinite loop where you need to use a break to end it.
``` rust
let mut attempts = 0;

loop {
    println!("Connecting...");
    attempts += 1;
    if attempts >= 3 {
        println!("Failed after 3 attempts.");
        break;
    }
}
```
- `while` is a long running loop that is base on if the statement is true
```rust
let mut battery_percentage = 100;

while battery_percentage > 0 {
    println!("Battery: {}%", battery_percentage);
    battery_percentage -= 10;
}
```
