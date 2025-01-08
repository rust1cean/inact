# inact

The entire syntax is built around higher and lower order functions.

## Implementation

- Written in Rust
- No garbage collector
- Higher order functions are writing in *PascalCase*
- Lower order functions are writing in *snake_case*

## Notes

- Higher-order functions replaces structures
- Higher-order functions have no variables
- Side-effects for holidays😁

## Examples

`./examples/hello_world.in`

```inact
act Main:
    hello("world")

act hello(who: str):
    println!("Hello, {who}!")
```

`./examples/calc.in`

```inact
act Main:
    Sum(1..10).then(|sum| println!("Sum is {sum}"))

act where T: Add & Debug
Sum(..args: Many<T>) -> T:
    args.pairs(Self::add)

    pub act add(a: T, b: T) -> T:
        a + b
```

`./examples/todo.in`

```inact
act Main:
    Todo.add("Design", "Read")

act Todo:
    pub act add(self, ..names: Many<str>) -> Self:
        todo!
```
