---
layout: post
title: "📜 ref and ref mut"
index_title: "ref and ref mut"
tags: [rustposts, rust]
---

The ```ref``` keyword is used to get references.

Here, the r inside the match has the type &i32. In other words, the ref keyword creates a reference, for use in the pattern:

```rust
let x = 5;

match x {
    ref r => println!("Got a reference to {}", r), // prints Got a reference to 5.
}
```

If its necessary to use a mutable reference use ```ref mut```:

```rust
let mut x = 5;

match x {
    ref mut mr => println!("Got a mutable reference to {}", mr),
}
```
