# Py2Strap

> pps is pypy bootstrapper that uses Python tricks to aim to simplify setting up and running code.
> because coding should be fun AND fast.

Quick start:

With strucs

```shell
./setup latest myapp
./run pps myapp/src/main
```

Without strucs:

```shell
./setup latest
# create your usual Hello, World!
./run pps hello.py
```

## Why pps

### Explicit imports

> No forced `.py` ext, no packages/modules or relative imports, or `__init__.py` annoying files.

```python
greet = load_mod("utils/greet")
# use a def of module
greet.say("World")
# or single/multiple functions
say = load_def("utils/greet", "say")
say("World")
# or run a mod directly
load_run("utils/greet")
```

### Ruff built-in

Ruff ships with pps via pypy pip -- no system install needed.

```shell
# lint entire project
./run pps -l .
# lint specific file
./run pps -l test/src/bad
```

Auto-discovers `pyproject.toml` by walking up from the target path. Ships with many rules pre-defined (to act as a kind of compiler/helper)


