# GLanguage
Linguagem de script

### Instalar `cli`

Build from source usando cargo:

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
