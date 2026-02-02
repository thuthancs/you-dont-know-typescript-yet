# you-dont-know-typescript-yet

## JS vs. TS
- TS is all about **type safety**, which prevents your programs from doing _invalid_ things. E.g., your function expects a list of strings, but you pass in a list of objects.
- JS, on the other hand, instead of throwing exceptions when those invalid things occur, tries to make the best of it and avoids exceptions.
  ```js
  3 + [] // evaluates to "3" instead of throwing an error
  
  function a(b) {
    return b/2
  }
  a("z") // evaluates to NaN
  ```
- As a result, you only become aware of your mistake when you _actually run_ your program when using JS. But if you use TS, you get _error messages in your IDE as you type_.
- **Mental model shift**: Sketch out a program at the type level before filling in the value level. You will think about edge cases as you design your program, not as an afterthought.
  
### TS Compiler 
- Programs are files containing text written by us. The text is parsed by a special program called a _compiler_, which transforms it into an _abstract syntax tree (AST)_, a data structure that ignores things like whitespace, comments, etc. The compiler converts that AST to a lower-level representation called bytecode. You can feed that bytecode into another program called a _runtime_ to evaluate it and get a result.
- TS compiles to JS code first before compiling straight to bytecode.
- After the TS Compiler generates an AST for your program, it _typechecks_ your code.
  
### The Type System
> A set of rules that a typechecker uses to assign types to your program
- Explicit: explicitly annotate your types `value: type`
  ```ts
  let a: number = 1
  let b: string = 'hello'
  let c: boolean[] = [true, false]
  ```
- Implicit: let TS infer most of them for you
  ```ts
  let a = 1
  let b = 'hello'
  let c = [true, false]
  ```

| type system feature | js | ts |
|---|---|---|
| how are types bound? | dynamically | statically |
| are types automatically converted? | yes | no |
| when are types checked? | at runtime | at compile time |
| when are errors surfaced? | at runtime (mostly) | at compile time (mostly) |

## books
1. Programming TypeScript: Making Your JavaScript Applications Scale (Boris Cherny)
