# Syntax
## Basics
(Any statement that doesn't specify otherwise ends with a semicolon)
### Variables
You can define variables in Xenon with the keyword `let`, then the variable identifier. Type inference is not supported yet, so it is required to specify the data type on creation.
```
let foo: i64;
let bar: bool = false;
```
Variables are immutable by default, if you wish to modify a variable, replace the `let` keyword with `mut` in the variable definition.
```
mut foo: string = "Hello world!";
foo = "Xenon > Solstice";
```
### Functions
Functions are Xenon are defined with the syntax of the return type (`void` for nothing), the function identifier, then parentheses containing the parameters. It is also required to define the type of function parameters, including the `mut` prefix if mutable, and a default value if optional. Functions in Xenon return a value with either the `return` keyword followed by the value and a semicolon, or just the value without a semicolon (similar to Rust and Solstice). Function definitions do NOT require a semicolon
```
i64 add(a: i64, b: i64) {
  a + b // returns the output of the expression
}
i64 subtract(a: i64, b: i64 = 10) {
  return a - b;
}
```
To call a function, you simply use its identifier followed by parentheses containing the parameters. Function calling DOES require a semicolon.
```
void main() {
  let foo = multiply(15, -34); // -510
  let bar = multiply(16); // 16
}

i64 multiply(a: i64, b: i64 = 1) {
  a * b
}
```