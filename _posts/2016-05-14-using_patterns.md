---
layout: post
title: "📜 Using Patterns"
index_title: "Using Patterns"
tags: [rustposts, rust, intermediate]
---

## Mix

There are many ways to match patterns and it's possible even mix then:

```rust
match x {
    Foo { x: Some(ref name), y: None } => ...
}
```

## Expression and statement-oriented

Unlike many languages that offer pattern matching, Rust embraces both statement- and expression-oriented programming.

This function maps a non-negative integer to a string rendering it as an ordinal (“1st”, “2nd”, “3rd”, …):

```rust
fn num_to_ordinal_expr(x: u32) -> String {
    format!("{}{}", x, match (x % 10, x % 100) {
        (1, 1) | (1, 21...91) => "st",
        (2, 2) | (2, 22...92) => "nd",
        (3, 3) | (3, 23...93) => "rd",
        _                     => "th"
    })
}
```
[Source](http://blog.rust-lang.org/2015/04/17/Enums-match-mutation-and-moves.html)