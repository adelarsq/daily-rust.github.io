---
layout: post
title: "📜 Variable Bindings"
index_title: "Variable Bindings"
tags: [rustposts, rust, beginner]
---


In many languages, a variable binding would be called a variable, but Rust’s variable bindings have a few tricks up their sleeves. For example the left-hand side of a let expression is a ‘pattern’, not a variable name.

```rust
let (x, y) = (1, 2); // x will be one, and y will be two

let z: i32 = 5; // x is a integer from 32 bits

let mut k = 5; // by default are variables a immutable. So to allow mutability use mut
```
