---
layout: post
title: "📜 Functions"
index_title: "Functions"
tags: [rustposts, rust]
---

Every Rust program has at least one function, the main function:

```rust
fn main() {
   // here is where the code remains
}
````

Here’s a complete program that uses a functions called print_number:

```rust
fn main() {
    print_number(5); // prints x is: 5
}

fn print_number(x: i32) {
    println!("x is: {}", x);
}
```

Here’s a complete program that adds two numbers together and prints them:

```rust
fn main() {
    print_sum(5, 6); // prints sum is: 11
}

fn print_sum(x: i32, y: i32) {
    println!("sum is: {}", x + y);
}
```

What about returning a value?

```rust
fn add_one(x: i32) -> i32 {
    x + 1
}

fn add_two(x: i32) -> i32 {
    let y: i32 = 2;
    x + y
}
```

