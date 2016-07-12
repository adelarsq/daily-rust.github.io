---
layout: post
title: "📜 Fibonacci"
index_title: "Fibonacci"
tags: [rustposts, rust, algorithm]
---

```rust
fn fibonacci(x: i32) -> i32 {
    if x <= 2 {
        return 1;
    } else {
        return fibonacci(x - 1) + fibonacci(x - 2);
    }
}

fn main() {
    let mut i: i32 = 1;

    while i <= 16 {
        println!("{}, ", fibonacci(i));
        i = i + 1;
    }
    println!("...");
}
```
