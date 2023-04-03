# PL/0


> pl0 is similar to but much simpler than the general-purpose programming language Pascal, intend as an educational programming language. 
> It serves as an example of how to construct a compiler.

## Grammar

```ebnf
 program = block "." .
 
 block =
     ["const" ident "=" number {"," ident "=" number} ";"]
     ["var" ident {"," ident} ";"]
     {"procedure" ident ";" block ";"} statement .
 
 statement =
     ident ":=" expression
     | "call" ident
     | "begin" statement {";" statement } "end"
     | "if" condition "then" statement
     | "while" condition "do" statement .
 
 condition =
     "odd" expression
     | expression ("="|"#"|"<"|"<="|">"|">=") expression .
 
 expression = ["+"|"-"] term {("+"|"-") term} .
 
 term = factor {("*"|"/") factor} .
 
 factor =
     ident
     | number
     | "(" expression ")" .
```

## Try it out!

1. Install [Rust](https://rustup.rs/)
2. Run the app
```bash
cargo run --release FILE
```
