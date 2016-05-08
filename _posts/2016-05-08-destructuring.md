---
layout: post
title: "Destructuring"
index_title: "Destructuring"
tags: [rustposts, rust]
---

If you have a compound data type, like a struct, you can destructure it inside of a pattern:

```rust
struct Point {
    x: i32,
    y: i32,
}
let origin = Point { x: 0, y: 0 };

match origin {
    Point { x, y } => println!("({},{})", x, y),
}

// Use : to give a different name
match origin {
    Point { x: x1, y: y1 } => println!("({},{})", x1, y1),
}

// If don't care about the values
match origin {
    Point { x, .. } => println!("x is {}", x),
}

// .. can match any member
match origin {
    Point { y, .. } => println!("y is {}", y),
}
```
