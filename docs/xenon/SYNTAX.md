# Syntax
## Basics
(Any statement that doesn't specify otherwise ends with `;`)
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