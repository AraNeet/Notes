## Types:
- Integers
- Floats
- Booleans
- Characters

## Integer types:
- Integers includes `i32`, `u32`, `i64`, and `u64`
- i stands for Signed, and U stands for Unsigned
- `32` and `64` indicates how much space the integer uses in memory.
``` Rust
 let x: i32 = -5; // A signed 32-bit int
 let y: u64 = 500020202; // An unsigned 64-bit integer
```
- When rust is inferring an integer it always infers i32. If the value is bigger then i32 type annotation is required.
``` rust
let y = 50000000000 // compile time error
// So you annotate the type 
let y: u64 = 500000000
```

## Float Types
- Floats can be `f32`, or `f64`. 
- `f32`. Is precise up to 7 decimal places. It's used where speed is more important then accuracy
- `f64`. Is precise up to 15 decimal places. It's used where accuracy is more important then speed
``` rust
let x: f32 = 3.1415926
let y: f64 = 3.131592653589793
```
- When inferring rust infer that a float value is `f64`.

## Boolean Types
- Bool is a bool

## Character types
- Char are only single unicode characters, like `a` or `😀`
``` rust
let Smile = '😀' // Inferred type as Char
```

We covered the 4 scalar data types that Rust supports:

- **Integer** types (`i8`, `i16` …)
    - Signed (`i*`) and unsigned (`u*`) integers with different sizes.
- **Floating-point** types (`f32`, `f64`)
    - `f32` (single precision) and `f64` (double precision).
- The **Boolean** type (`bool`)
    - `true` or `false`.
- The **Character** type (`char`)
    - Represents a Unicode scalar value (e.g., 'a', '😊').

You can learn more about these in the [Data Types](https://doc.rust-lang.org/book/ch03-02-data-types.html) chapter of the Rust book.