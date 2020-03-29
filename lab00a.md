# ES6 *let* and *const*
## LET
 - The let statement declares a block scope local variable, optionally initializing it to a value.
 - In ECMAScript 6, let will hoist the variable to the top of the block. However, referencing the variable in the block before the
   variable declaration results in a ReferenceError. The variable is in a “temporal dead zone” from the start of the block until the
   declaration is processed.

**why the name let was chosen**

JavaScript has had var from the beginning, so they just needed another keyword, and just borrowed from dozens of other languages that use
let already as a traditional keyword as close to var as possible, although in JavaScript let creates block scope local variable instead.


Scoping Rules:
```
function letTest() {
  let x = 1;
  {
    let x = 2;  // different variable
    console.log(x);  // 2
  }
  console.log(x);  // 1
}
```
let, unlike var, does not create a property on the global object. For example:
```
var x = 'global';
let y = 'global';
console.log(this.x); // "global"
console.log(this.y); // undefined
```
**Redeclarations:**

  - Redeclaring the same variable within the same function or block scope raises a **SyntaxError**.
  
**Temporal dead zone**
  - let variables are not initialized until their definition is evaluated. Accessing the variable before the initialization 
  results in a **ReferenceError**.
```
function do_something() {
  console.log(foo); // ReferenceError
  let foo = 2;
}
```
## CONST
- Constants are block-scoped
- The value of a constant can't be changed through reassignment, and it can't be redeclared.




