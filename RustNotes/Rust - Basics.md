## Variables
- By default variable are immutable and use ``` let ``` to define it
- If you want to make it mutable ``` let mut ``` is the way to define it
## Print functions
-  ``` println!(with newline) or print!(without newline) ``` is the way to print to the stdout.
- ``` eprintln! and eprint!``` is the way to print to the stderr(standard error stream).
## Types
-  Type are define like ``` let car: type goes here ``` 
-  Type are not need for the code to work. The complier can infer it.
-  Rust has 4 scalar types — integers, floating-point numbers, booleans, and characters.
-  Compound types are tuples and arrays. These are groups that can have multiple values into one type.
# Examples.
``` Rust
// Scalar types
 let a = 42; // Int
 let b = 4.2; // Float
 let c = true; // Boolean
 let b = 'a' // Char 

// Compound types
 let chess = (5, 'A');
 let array = [1, 2, 3];