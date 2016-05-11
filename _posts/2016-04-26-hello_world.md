---
layout: post
title: "📜 Hello World"
index_title: "Hello World"
tags: [rustposts, rust]
---

This is the source code of the traditional Hello World program.

```rust
// This is the main function
fn main() {
    // The statements here will be executed when the compiled binary is called

    // Print text to the console
    println!("Hello World!");
}
```

Comments starts with ```//```. See more on the follow [post](http://daily-rust.github.io/2016/04/27/comments.html)

```fn``` is the keyword used to declare a functions.

```println``` is a [macro](https://doc.rust-lang.org/book/macros.html). Macros allow us to abstract at a syntactic level, that allows avoid repeated code.

Strings are between ```"```.
