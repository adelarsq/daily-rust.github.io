---
layout: post
title: "📜 Factorial"
index_title: "Factorial"
tags: [rustposts, rust, algorithm]
---

```rust
fn factorial(x: u64) -> u64 {
    if x <= 1 {
        return 1;
    } else {
        return (x as u64) * factorial(x - 1);
    }
}

fn main() {
    let mut i = 0;
    while i <= 16 {
        println!("{} = {}", i, factorial(i));
        i = i + 1;
    }
}
```
