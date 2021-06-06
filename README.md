# GLanguage

> GLanguage Scripting Language written in Rust.

### Install `cli`

Build from source using cargo:

```bash
$ git submodule init
$ git submodule update

$ cargo build --release
```

### Getting Started

`REPL` (Read Eval Print Loop)

```bash
$ gl repl
```

`Eval` (Evaluate source from the command line)

```bash
$ gl eval "42"
```

`Run` (Run program from a script file)

```bash
$ gl run script.gl
```

`Fmt` (Format a script file)

```bash
$ gl fmt script.gl
```

## Documentation

- [Syntax overview](#syntax-overview)
    - [Operators](#operators)
- [Variable bindings](#variable-bindings)
- [Literals](#literals)
    - [Integer](#integer)
    - [Float](#float)
    - [Boolean](#boolean)
    - [String](#string)
    - [Vec](#vec)
    - [Tuple](#tuple)
    - [HashMap](#hashmap)
    - [Function](#function)


### Syntax overview

#### Operators

It supports the general operations.

```rust
1 + 2 + (3 * 4) - (10 / 5)
!true
!false
+10
-5
"Hello" + " " + "World"
```

### Variable bindings

Variable bindings, such as those supported by many programming languages, are implemented. Variables can be defined using the `let` keyword.

**Format:**

```rust
let <identifier> = <expression>
```

**Example:**

```rust
let x = 0
let y = 10
let function = fn(x) { x }
```

### Literals

Literals implemented.

#### Integer

`Integer` represents an integer value.

**Format:**

```rust
42
200
```

#### Float

`Float` represents an float value.

**Format:**

```rust
3.1415
```

#### Boolean

`Boolean` represents a general boolean types.

**Format:**

```rust
true | false
```

**Example:**

```rust
true
false

let truthy = !false
let falsy = !true
```

#### String

`String` represents a string. Only double quotes can be used.

**Format:**

```rust
"<value>"
```

**Example:**

```rust
"GLanguage"
"Hello" + " " + "World"
```

#### Vec

`Vec` represents an ordered contiguous element. Each element can contain different data types.

**Format:**

```rust
[<expression>, <expression>, ...]
```

**Example:**

```rust
[1, 2, 3 + 3, fn(x) { x }, add(2, 2), true]
```

```rust
let vec = [1, true, fn(x) { x }]

vec[0]
vec[1]
vec[2](10)
vec[1 + 1](10)
```


#### Tuple

`Tuple` represents an ordered contiguous element. Each element can contain different data types.

**Format:**

```rust
(<expression>, <expression>, ...)
```

**Example:**

```rust
(1, 2, 3 + 3, fn(x) { x }, add(2, 2), true)
```

#### HashMap

`HashMap` represents data associating keys with values.

**Format:**

```rust
{<expression>: <expression>, <expression>: <expression>, ...}
```

**Example:**

```rust
let hashmap = {
  "name": "José Carlos",
  "age": 17,
  true: "a boolean",
  42: "an integer"
  3.1415: "an float",
  fn (){}: "an function",
}

hashmap["name"]
hashmap["a" + "ge"]
hashmap[true]
hashmap[42]
hashmap[4.1415 - 1]
hashmap[fn (){}]
```

#### Function

`Function` supports functions like those supported by other programming languages.

**Format:**

```rust
fn (<parameter one>, <parameter two>, ...) { <block statement> };
```

**Example:**

```rust
let add = fn(x, y) {
  x + y
}

add(10, 20)
```

```rust
fn add(x, y) {
  x + y
};

add(10, 20)
```

If `return` does not exist, it returns the result of the last evaluated expression.

```rust
let add_three = fn(x) { x + 3 }
let call_two_times = fn(x, f) { f(f(x)) }

call_two_times(3, add_three)
```

## License

[MIT © Skalamark](./LICENSE)

