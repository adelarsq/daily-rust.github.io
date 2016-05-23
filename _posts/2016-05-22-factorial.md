---
layout: post
title: "📜 Factorial"
index_title: "Factorial"
tags: [rustposts, rust, algorithm]
---

```rust
use std;

import std::io;

fn factorial(x: int) -> uint {
  if (x <= 1) {
    ret 1u;
  } else {
    ret (x as uint) * factorial(x - 1);
  }
}

fn main() {
  let i = 0;
  while i <= 16 {
    io::println(#fmt("%d! = %u", i, factorial(i)));
    i = i + 1;
  }
}
```
