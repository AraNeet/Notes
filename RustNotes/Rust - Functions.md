- Functions are define with `fn`
```rust
fn sing() {
    println!("la la la LA LA");
}
```
- function parameters and return are defined like this 
```rust
fn add(x: i32, y: i32) -> i32 {
    x + y
}
```
- Return in functions can the last line of the expression. By default it's like this as long as there is no semicolon.
```rust
fn square(x: i32) -> i32 {
    x * x
}

let result = square(3);
println!(result); // 9
```
- An other way could be by adding the `return` keyword
```rust
fn square(x: i32) -> i32 {
    return x * x; // <-- also valid!
}
```
- **Function declaration**: Functions are declared using the `fn` keyword with typed arguments. Return types are defined using the `->` notation.
    
- **Expressive return mechanism**: In Rust, the value of the final expression in a function serves as its return value, provided it doesn't end with a semicolon. Ending an expression with a semicolon causes it to return `()`, an empty tuple.
    
- **Explicit `return` keyword**: Rust allows the use of the `return` keyword for early exits or clarity, but it's optional when returning the value of the final expression.
    

### Further reading

For a more comprehensive understanding of Rust's functions, consider referring to the [Rust book](https://doc.rust-lang.org/book/ch03-03-how-functions-work.html).