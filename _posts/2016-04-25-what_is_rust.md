---
layout: post
title: "📜 What is Rust?"
index_title: "What is Rust?"
tags: [rustposts, rust, beginner]
---

[Rust](https://www.rust-lang.org/index.html) is a systems programming language that runs blazingly fast, prevents segfaults, and guarantees thread safety.

This language exposes lower level concepts but using high level features like:

- zero-cost abstractions
- move semantics
- guaranteed memory safety
- threads without data races
- trait-based generics
- pattern matching
- type inference
- minimal runtime
- efficient C bindings
- **it's fun!**

Also has a growing number of tools. You can do [almost anything](https://github.com/kud1ing/awesome-rust), since [Web](https://github.com/kud1ing/awesome-rust#web-programming) stuff until [Operating Systems](https://github.com/kud1ing/awesome-rust#operating-systems).

It's a pretty new language (1.0 released on [May 15, 2015](http://blog.rust-lang.org/2015/05/15/Rust-1.0.html)), but is already been used in [many companies](https://www.rust-lang.org/friends.html) in production enviroment.

This is how the code looks like:

```rust
// This code is editable and runnable!
fn main() {
    // A simple integer calculator:
    // `+` or `-` means add or subtract by 1
    // `*` or `/` means multiply or divide by 2

    let program = "+ + * - /";
    let mut accumulator = 0;

    for token in program.chars() {
        match token {
            '+' => accumulator += 1,
            '-' => accumulator -= 1,
            '*' => accumulator *= 2,
            '/' => accumulator /= 2,
            _ => { /* ignore everything else */ }
        }
    }

    println!("The program \"{}\" calculates the value {}",
              program, accumulator);
}
```
[Run the code! ;)](https://play.rust-lang.org/?code=%2F%2F%20This%20code%20is%20editable%20and%20runnable!%0Afn%20main()%20%7B%0A%20%20%20%20%2F%2F%20A%20simple%20integer%20calculator%3A%0A%20%20%20%20%2F%2F%20%60%2B%60%20or%20%60-%60%20means%20add%20or%20subtract%20by%201%0A%20%20%20%20%2F%2F%20%60*%60%20or%20%60%2F%60%20means%20multiply%20or%20divide%20by%202%0A%0A%20%20%20%20let%20program%20%3D%20%22%2B%20%2B%20*%20-%20%2F%22%3B%0A%20%20%20%20let%20mut%20accumulator%20%3D%200%3B%0A%0A%20%20%20%20for%20token%20in%20program.chars()%20%7B%0A%20%20%20%20%20%20%20%20match%20token%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%27%2B%27%20%3D%3E%20accumulator%20%2B%3D%201%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%27-%27%20%3D%3E%20accumulator%20-%3D%201%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%27*%27%20%3D%3E%20accumulator%20*%3D%202%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%27%2F%27%20%3D%3E%20accumulator%20%2F%3D%202%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20_%20%3D%3E%20%7B%20%2F*%20ignore%20everything%20else%20*%2F%20%7D%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%7D%0A%0A%20%20%20%20println!(%22The%20program%20%5C%22%7B%7D%5C%22%20calculates%20the%20value%20%7B%7D%22%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20program%2C%20accumulator)%3B%0A%7D%0A&run=1)

Resources on the Web:

* [Roseta code examples](https://rosettacode.org/wiki/Category:Rust)
