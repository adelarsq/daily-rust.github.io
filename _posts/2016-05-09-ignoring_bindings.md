---
layout: post
title: "Ignoring bindings"
index_title: "Ignoring bindings"
tags: [rustposts, rust]
---

```_``` can be used in a pattern to disregard the type and value:

```rust
match some_value {
    Ok(value) => println!("got a value: {}", value),
    Err(_) => println!("an error occurred"),
}
```

```_``` is valid in any pattern that creates a binding. This can be useful to ignore parts of a larger structure:

```rust
fn coordinate() -> (i32, i32, i32) {
    // generate and return some sort of triple tuple
}

let (x, _, z) = coordinate();
```

```..``` can be used in a pattern to disregard multiple values:

```rust
enum OptionalTuple {
    Value(i32, i32, i32),
    Missing,
}

let x = OptionalTuple::Value(5, -2, 3);

match x {
    OptionalTuple::Value(..) => println!("Got a tuple!"),
    OptionalTuple::Missing => println!("No such luck."),
}
```
