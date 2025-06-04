Rust provides a borrowing system to access data without transferring ownership.

### The borrow symbol

The `&` symbol signifies a borrow.

```rust
let s = String::from("hello");
let borrowed_s = &s;
```

Borrowing comes in two flavors: immutable and mutable.

### Immutable borrows

An immutable borrow lets you **read** data, but not change it.

```rust
let s = String::from("hello");
let r1 = &s;
let r2 = &s;
```

### Mutable borrows

A mutable reference lets you **alter** data.

Only one mutable reference is allowed within a scope.

This ensures no data races.

```rust
let mut s = String::from("hello");

let r1 = &mut s;
let r2 = &mut s; // Error: cannot borrow `s` as mutable more than once

println!("{r1}, {r2}");
```

Multiple immutable borrows can coexist, but not alongside a mutable borrow.

```rust
let mut s = String::from("hello");

let r1 = &s;
let r2 = &s;
let r3 = &mut s; // This would be an error!

println!("{r1}, {r2}, {r3}");
```

Why does Rust allow only one mutable reference to data in a particular scope?

To prevent potential data races

To reduce memory usage

To execute efficient code

To support parallel processing

SubmitShow explanation

### Dangling references

Dangling is when a reference's data gets freed while the reference still exists.

Rust ensures references never "dangle".

```rust
let r; 
{
    let s = String::from("hello");
    r = &s;  
} // `s` drops here, making `r` a dangling reference.
```

In the below code example, what is the primary reason Rust prevents the use of the variable `r` after the inner block?

```rust
let r; 
{
    let s = String::from("hello");
    r = &s;  
} // `s` is dropped here
```

To optimize memory usage

To dodge potential runtime errors

Because `r` was never properly initialized.

To prevent dangling references

SubmitShow explanation

### Slices: a quick look

Slices let you reference collection parts, not the entire collection.

This way, you can work with collection segments without owning the whole thing.

This allows for flexible and safe data access.

```rust
let string = String::from("Hello, World!");
let hello_slice = &string[0..5]; // hello_slice = "Hello"
let world_slice = &string[7..12]; // world_slice = "World"
```

What's the main benefit of slices?

Work with parts without owning the entire collection

Directly alter the original data

It consumes less memory

They boost code execution speed

Submit Show explanation

### Summary

Rust promotes safe data handling through its borrowing mechanism, allowing data access without complete ownership transfer:

- **Immutable references**: Read data without altering. Multiple immutable references can coexist unless there's a mutable reference.
    
- **Mutable references**: Modify data. Only one is allowed per scope.
    
- **Dangling references**: Rust ensures all references point to valid data.
    
- **Slices**: Let you reference collections in parts
    

### Further reading

The power of Rust's ownership and borrowing rules lies in ensuring memory safety and data integrity without the need for a garbage collector. Please check out the [Rust Book](https://doc.rust-lang.org/book/ch04-02-references-and-borrowing.html).