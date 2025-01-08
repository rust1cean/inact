# inact

The entire syntax is built around higher and lower order functions.

## Implementation

- Written in Rust
- No garbage collector
- Higher order functions are writing in *PascalCase*
- Lower order functions are writing in *snake_case*

## Notes

- Higher-order functions replace structures
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

act where T: Add
Sum:
    pub act main(...args: Many<T>) -> T:
        args.pairs(Self.add)

    pub act add(a: T, b: T) -> T:
        a + b
```
