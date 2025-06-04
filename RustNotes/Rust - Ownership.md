- In rust ownership is the way to manage pieces of data
- tranferring ownership for complex type is transfer like this
```rust
let s1 = String::from("hello");
let s2 = s1;  // Ownership passes from s1 to s2

println!("{}", s2); // "hello"
// println!("{}", s1); // This would error because s1 can no longer be used
```
- For simple type it would just make a copy
```rust
let num1 = 5;
let num2 = num1;  // num1 is copied, not transferred

println!("{}", num1); // 5, Totally valid!
println!("{}", num2); // 5, Also valid!
```
- Rust categorizes data types into `Copy` and `non-Copy`.

- **Copy:** Simple scalar types like integers, bool, and characters.

When assigned to another variable, they get copied.

The original remains untouched.

For instance:

```rust
let is_active = true;
let is_duplicate = is_active;

println!("{}", is_active); // "true"
println!("{}", is_duplicate); // "true"
```

- **Non-Copy**: Types such as `String` or `Vec`.

When assigned, they transfer ownership, making the original unusable.

For instance:

```rust
let text1 = String::from("Hello, world!");
let text2 = text1;

println!("{}", text2); // Outputs: Hello, world!
// println!("{}", text1); // This would error because text1 can no longer be used
```
- **Ownership in Rust**: Rust has a unique ownership model for memory safety. Each data piece has one owner, and using a variable after transferring its ownership leads to an error, ensuring that data isn't modified from multiple locations at the same time.
    
- **Complex data type ownership**: Types like `String` strictly adhere to Rust's ownership model. Once their ownership is transferred to another variable, the original becomes unusable.
    
- **Simple data type copy behavior**: Unlike complex types, simple data types such as integers implement the `Copy` trait. This means they get duplicated when assigned to another variable, leaving the original variable intact and usable.
    

### Further reading

Understanding Rust's ownership model is key for safe and efficient Rust programming. Please read the [Rust Book](https://doc.rust-lang.org/book/ch04-01-what-is-ownership.html).