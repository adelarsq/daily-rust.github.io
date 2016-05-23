---
layout: post
title: "📜 Fibonacci"
index_title: "Fibonacci"
tags: [rustposts, rust, algorithm]
---

```rust
use std;

import std::io;

fn fibonacci(x: int) -> int {
  if (x <= 2) {
    ret 1;
  } else {
    ret fibonacci(x - 1) + fibonacci(x - 2);
  }
}

fn main() {
  let i = 1;
  let v: Vec<_> = vec![1,2,3];

  while i <= 16 {
    io::print(#fmt("%d, ", fibonacci(i)));
    i = i + 1;
  }
  io::println("...");
}
```
