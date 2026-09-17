# Syntax
## Basics
### Variables
When defining variables in Xenon, we start with the `let` keyword, then the variable identifier (in this example `foo`) and value (`16`).

```
let foo = 16;
```

Of course the value initialisation is optional, so we can create a variable to initialise later with `let foo;`.

Type inference in Xenon is planned, but not yet reliable so it's generally better practice to annotate your variables.
```
let foo: i32;
let bar: bool = false;
```

Variables are immutable by default, so if you wish to modify your variables you replace the `let` keyword with `mut`:
```
mut foo: string = "Hello world!";
foo = "Xenon > Solstice";
```

For precompiled variables, add the suffix `const`. Const variables require type annotation (for now), and can be placed in the global scope to be accessed from anywhere in the file (unlike normal variables).
```
const PRECOMPILED: i32 = 15 * 2;

void main() {
  let x = PRECOMPILED;
}
```

Another suffix we can use is `static`, which works the same as a const in the global scope, except it can be mutable. If used in a smaller scope, the value retains over all iterations of that scope.
```
void main() {
  for i in 0..1_000 { count(); }
  let final_n = count();
}

i64 count() {
  static n: i64 = 0;
  n++;
  n
}
```