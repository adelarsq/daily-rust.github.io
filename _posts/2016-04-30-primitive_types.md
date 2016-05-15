---
layout: post
title: "📜 Primitive Types"
index_title: "Primitive Types"
tags: [rustposts, rust, beginner]
---

### Booleans

```rust
let x = true;
let y: bool = false;
````

### Char

```rust
let x = 'x';
let two_hearts = '💕';
```

### Numeric Types

Possible numeric types are i8, i16, i32, i64, u8, u16, u32, u64, isize, usize, f32, f64. Unsigned types use a u for their category, and signed types use i.

```rust
let x = 42; // x has type i32
let y = 1.0; // y has type f64
let z:i32 = 64; // z has type i32
```

### Arrays

```rust
let a = [1, 2, 3]; // a: [i32; 3]
let mut m = [1, 2, 3]; // m: [i32; 3]
```

### Slice or "view"

```rust
let a = [0, 1, 2, 3, 4];
let complete = &a[..]; // A slice containing all of the elements in a
let middle = &a[1..4]; // A slice of a: only the elements 1, 2, and 3
```

### str

Rust’s str type is the most primitive string type. As an unsized type, it’s not very useful by itself, but becomes useful when placed behind a reference, like &str.

```rust
let s: &str = "Hello";
```

### Tuples

```rust
let x1 = (1, "hello");
let x2: (i32, &str) = (1, "hello");
let tuple = (1, 2, 3);
let x = tuple.0;
let y = tuple.1;
let z = tuple.2;
println!("x is {}", x);
```

### Functions

```rust
fn foo(x: i32) -> i32 { x }
let x: fn(i32) -> i32 = foo;
```

