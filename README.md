## What is cargo?
Cargo is a package manager. Cargo is used for search, install and manage
packages that you want to use. Cargo is also the build system. Cargo
is also the test runner and the documentation generator etc. Is like npm or pip

If you do: ``cargo new hello`` Cargo will create a named hello with
a subdirectory with a main.rs file. Config files in rust use the .toml
format(Toms obvious minimal language). Rust source files use the .rs extension.

If you open the .toml file you will see something like this:

```toml
[package]
name = "hello"
version = "0.1.0"
edition = "2021"

# See more keys and their definitions at https://doc.rust-lang.org/cargo/reference/manifest.html

[dependencies]

```
Where:
- name: Thee name of the project. This setting determines the name of
  of your project. 
- version: Rust uses semantic versioning, which means a version number is always three
  numbers separated by dots and each number has a specific meaning. Go to
  [semver.org](semver.org) for more details.

**cargo run** is the command to build and run your project in one step

Cargo compiles your project with debug symbols by default.

Add --release to you ```cargo run``` command to compile without debug symbols. 
```cargo run --release```

Most of code will run significantly faster in release mode, but it takes a little longer to compile.

## Variables 

Declaring and initialize the variable "bunnies"  with value of 2. 

```rust
let bunnies = 2;
```
Rust is a strongly typed language, Rust can figure out the appropriate type  for you
and just can leave the type annotation. 

Whn you do annotate the type it looks like thi: 
```rust
let bunnies: i32 = 4;
```
Variables are immutable by default in Rust, which means unless you choose to make them 
mutable you can't ever change their value.


To make that a variable can be mutable we need to specify the mutability of the variable as follows:
```rust
let mut bunnies = 32;
bunnies = 2;
```
There is also a kind of variable that is even immutable: the **constant** 

There are four things different about declaring a constant: 
- First **const** instead of **let**
- The convention is use screaming-snake-case for constant which means all uppercase
  case separated by underscores 
- The **type** annotation is required
- The value must be a constant expression that can be determined at compile time. A literal always works just 
  fine.

```rust
const WARP_FACTORL: f64 = 9.9;
```

You can place a constant outside of a function at module scope and use it anywhere you want. 
A global, an immutable, constant global. 

## Primitive Types

- i32: 32 bit integer

## Functions

Functions are defined using the "fn" keyword. The rust style guide says
to use snake-case for function names(my_function_name), as you could see
lowers words separated by underscores. The functions dont have to appear 
in the file before the code that calls them, so feel free to leave whatever you 
want.

```rust
fn main() {
  do_stuff();
}

fn do_stuff() {
  
}
```

Functions parameters are always defined with "name:type" and of course
multiple parameters are separated by a comma. 
Your specify the return type after the parameters by adding an arrow 
pointing to the return type. And the body of the funcion is inside 
a block, you return values of the function with the keywork **return**

```rust
fn do_stuff(qty: f64, oz: f64) -> f64 {
  return qty * oz;
}
```

If you leave the semicolon off of the last expression in a block then it wil 
be returned as the value of the block. 
```rust
fn do_stuff(qty: f64, oz: f64) -> f64 {
   qty * oz;
}
```

This is called a "tail expression" so this: 
```rust 
{ return true}
```

is the same as this:
```rust
{ true }
```
