---
layout: post
title: "📜 Factorial"
index_title: "Factorial"
tags: [rustposts, rust, algorithm]
---

```rust
fn factorial(x: u64) -> u64 {
    if x <= 1 {
        1
    } else {
        (x as u64) * factorial(x - 1)
    }
}

fn main() {
    for i in 0..17 {
        println!("{} = {}", i, factorial(i));
    }
}
```
