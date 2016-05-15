---
layout: post
title: "📜 Cheatsheet"
index_title: "Cheatsheet"
tags: [rustposts, rust, article]
---

# Rust Cheatsheet

- 1 How do I convert X to Y?
- 2 File operations
- 2.1 How do I read from a file?
- 2.2 How do I iterate over the lines in a file?
- 3 String operations
- 3.1 How do I search for a substring?
- 4 Containers
- 4.1 How do I get the length of a vector?
- 4.2 How do I iterate over a vector?
- 5 Type system
- 5.1 How do I store a function in a struct?
- 5.2 How do I express phantom types?
- 6 FFI (Foreign Function Interface)
- 6.1 C function signature conversions
- 6.1.1 Representing opaque handles
- 7 Contributing to this page

Based on: http://static.rust-lang.org/doc/0.9/complement-cheatsheet.html

## 1 How do I convert X to Y?

**Int to string**
Use ToStr.

```rust
let x: int = 42;
let y: ~str = x.to_str();
```
**String to int**

Use FromStr, and its helper function, from_str.

```rust
let x: Option<int> = from_str("42");
let y: int = x.unwrap();
```

**Int to string, in non-base-10**

Use ToStrRadix.

```rust
use std::num::ToStrRadix;
let x: int = 42;
let y: ~str = x.to_str_radix(16);
```

**String to int, in non-base-10**

Use FromStrRadix, and its helper function, from_str_radix.

```rust
use std::num::from_str_radix;
let x: Option<i64> = from_str_radix("deadbeef", 16);
let y: i64 = x.unwrap();
```

## 2 File operations

### 2.1 How do I read from a file?
Use File::open to create a File struct, which implements the Reader trait.

```rust
use std::path::Path;
use std::io::fs::File;

let path : Path   = Path::new("Doc-FAQ-Cheatsheet.md");
let on_error      = || fail!("open of {:?} failed", path);
let reader : File = File::open(&path).unwrap_or_else(on_error);
```

### 2.2 How do I iterate over the lines in a file?
Use the lines method on a BufferedReader.

```rust
use std::io::buffered::BufferedReader;

let mut reader = BufferedReader::new(reader);
for line in reader.lines() {
    print!("line: {}", line);
}
```

## 3 String operations

3.1 How do I search for a substring?
Use the find_str method.

let str = "Hello, this is some random string";
let index: Option<uint> = str.find_str("rand");

## 4 Containers

### 4.1 How do I get the length of a vector?
The Container trait provides the len method.

```rust
let u: ~[u32] = ~[0, 1, 2];
let v: &[u32] = &[0, 1, 2, 3];
let w: [u32, .. 5] = [0, 1, 2, 3, 4];

println!("u: {}, v: {}, w: {}", u.len(), v.len(), w.len()); // 3, 4, 5
```

### 4.2 How do I iterate over a vector?
Use the iter method.

```rust
let values: ~[int] = ~[1, 2, 3, 4, 5];
for value in values.iter() {  // value: &int
    println!("{}", *value);
}
```
(See also mut_iter which yields &mut int and move_iter which yields int while consuming the values vector.)

## 5 Type system

### 5.1 How do I store a function in a struct?

```rust
struct Foo {
    myfunc: fn(int, uint) -> i32
}

struct FooClosure<'a> {
    myfunc: 'a |int, uint| -> i32
}

fn a(a: int, b: uint) -> i32 {
    (a as uint + b) as i32
}

fn main() {
    let f = Foo { myfunc: a };
    let g = FooClosure { myfunc: |a, b|  { (a - b as int) as i32 } };
    println!("{}", (f.myfunc)(1, 2));
    println!("{}", (g.myfunc)(3, 4));
}
```
Note that the parenthesis surrounding f.myfunc are necessary: they are how Rust disambiguates field lookup and method call. The 'a on FooClosure is the lifetime of the closure's environment pointer.

### 5.2 How do I express phantom types?
Phantom types are those that cannot be constructed at compile time. To express these in Rust, zero-variant enums can be used:

```rust
enum Open {}
enum Closed {}
````

Phantom types are useful for enforcing state at compile time. For example:

```rust
struct Door<State>(~str);

struct Open;
struct Closed;

fn close(Door(name): Door<Open>) -> Door<Closed> {
    Door::<Closed>(name)
}

fn open(Door(name): Door<Closed>) -> Door<Open> {
    Door::<Open>(name)
}

let _ = close(Door::<Open>(~"front"));
```
Attempting to close a closed door is prevented statically:

```rust
let _ = close(Door::<Closed>(~"front")); // error: mismatched types: expected `main::Door<main::Open>` but found `main::Door<main::Closed>`
````

## 6 FFI (Foreign Function Interface)

### 6.1 C function signature conversions
Description	| C signature |	Equivalent Rust signature
----------- | ----------- | -------------------------
no parameters | ```void foo(void);``` | ```fn foo();```
return value | ```int foo(void);``` | ```fn foo() -> c_int;```
function parameters | ```void foo(int x, int y);``` | ```fn foo(x: int, y: int);```
in-out pointers | ```void foo(const int* in_ptr, int* out_ptr);``` | ```fn foo(in_ptr: *c_int, out_ptr: *mut c_int);```

Note: The Rust signatures should be wrapped in an ```extern "ABI" { ... }``` block.

#### 6.1.1 Representing opaque handles
You might see things like this in C APIs:

```rust
typedef struct Window Window;
Window* createWindow(int width, int height);
```

You can use a zero-element enum (phantom type) to represent the opaque object handle. The FFI would look like this:

```rust
enum Window {}
extern "C" {
    fn createWindow(width: c_int, height: c_int) -> *Window;
}
```

Using a phantom type ensures that the handles cannot be (safely) constructed in client code.

## 7 Contributing to this page

For small examples, have full type annotations, as much as is reasonable, to keep it clear what, exactly, everything is doing. Try to link to the API docs, as well.

Similar documents for other programming languages:

http://pleac.sourceforge.net/
