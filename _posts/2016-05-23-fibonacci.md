---
layout: post
title: "📜 Fibonacci"
index_title: "Fibonacci"
tags: [rustposts, rust, algorithm]
---

```rust
fn fibonacci(x: i32) -> i32 {
    if x <= 2 {
        1
    } else {
        fibonacci(x - 1) + fibonacci(x - 2)
    }
}

fn main() {
    for i in 1..17 {
        println!("{}", fibonacci(i));
    }
}
```
