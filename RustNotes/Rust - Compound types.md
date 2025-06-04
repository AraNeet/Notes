## Tuples
- Tuples are a group type that store multiple values.
- The length of the tuples is fixed. The values must always contain the same number of elements
``` rust
let tuple_with_2_ints: (i32, i32) = (1, 2);
let tuple_with_3_ints: (i32, i32, i32) = (1, 2, 3);

// This is invalid because the value has < 3 elements
// let tuple_with_3_ints: (i32, i32, i32) = (1, 2);

// This is invalid too because the value has > 3 elements
// let tuple_with_3_ints: (i32, i32, i32) = (1, 2, 3, 4);
```

- Tuples can have different type of values but the type signature needs to match.
``` rust
let tuple_with_int_and_char: (i32, char) = (1, 'A');

// This is a compile-time error because the value has 'char' as the first type, not 'i32'. 
// let tuple_with_int_and_char: (i32, char) = ('A', 1);
```

- They infer based on the values given in the define.
``` rust
// Here the inferred type is (i32, char)
let tuple_with_int_and_char = (1, 'A');
```
- Accessing the different values it done by `<variable>.<index>`
- Tuples can be destructed. by 
``` rust
let chess_square = ('A', 5);
let (column, row) = chess_square; // column is 'A', row is 5.
```
- It will assign the value by order.
- If you want to destruct you need to have to correct number of the variable.
``` rust
let chess_square = ('A', 5);

// This fails because the left-hand side only contains one value
// let (column) = chess_square;

// This fails because the left-hand side only contains >2 values
// let (column, row, index) = chess_square

// This works because the left-hand side contains exactly 2 values
let (column, row) = chess_square;
```
In this concept we covered Tuples, a Rust data type that is used to group multiple values.

- Tuples have a fixed length
- Tuples can contain elements of multiple types
- Tuples types are defined using parentheses like this: `(char, i32)`
- Elements in a tuple can be accessed using two methods:
    - Indexing — `chess_square.0`, `chess_square.1`
    - Destructuring — `let (row, column) = chess_square`

You can read more about the tuple data type in the [Data Types](https://doc.rust-lang.org/book/ch03-02-data-types.html) section of the Rust book.

## Arrays
- Arrays are for storing multiple values of the same types.
- Arrays are defined like
``` rust
// An array
let checks: [bool; 3] = [true, false, true];
```
- Like tuples array have fixed length
``` rust
let array_with_2_ints: [i32; 2] = [1, 2];
let array_with_3_ints: [i32; 3] = [1, 2, 3];

// This is invalid because the value has < 3 elements
// let array_with_3_ints: [i32; 3] = [1, 2];

// This is invalid too because the value has > 3 elements
// let array_with_3_ints: [i32; 3] = [1, 2, 3, 4];
```
- When type inferring the array it infers the length.
``` rust
// Here the inferred type is [i32; 3]
let array_with_3_ints = [1, 2, 3];
```
 - Accessing and destructing is similar to tuples 
``` rust
let array_of_3_ints = [1, 2, 3];

// Indexation
array_of_3_ints[0] // => Returns 1
array_of_3_ints[1] // => Returns 2
array_of_3_ints[2] // => Returns 3

// Destructuring
let [a1, a2, a3] = array_of_3_ints; // Assigns a1 to 1, a2 to 2 and a3 to 3
```
In this concept we covered Arrays, a Rust data type that is used to group multiple values of the same type.

- Arrays have a fixed length
- Arrays must contain elements of the same type
- Array types are defined using square brackets like this: `[i32; 4]`
- Elements in an array can be accessed using two methods:
    - Indexing — `array_of_values[0]`, `array_of_values[1]`
    - Destructuring — `let [a1, a2, a3] = array_of_values`

You can read more about the array data type in the [Data Types](https://doc.rust-lang.org/book/ch03-02-data-types.html) section of the Rust book.
