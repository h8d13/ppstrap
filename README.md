# Py2Strap

> pps is pypy bootstrapper that uses Python tricks to aim to simplify setting up and running code.
> because coding should be fun AND fast.

Quick start:

```shell
./setup latest                  # pypy + pip
./setup latest myapp            # + project structure (src/utils)
./setup latest myapp lint       # + ruff + pyproject.toml
./setup v7.3.19 myapp lint      # specific pypy version

# for the purists:
NO_PIP=1 ./setup latest         # bare pypy, no pip
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

### All flags

```
# run is symlinked originally to the extract .pypy{version}/bin/pypy3.11

./run pps <script>          run a script
./run pps -v                show pypy path and version
./run pps -i pkg1 pkg2      install packages (with dep tracking)
./run pps -f requirements   install from requirements file
./run pps -u pkg1 pkg2      uninstall packages (with dep cleanup)
./run pps -l [path]         lint with ruff (defaults to .)
./run pps -r                nuke pypy installation (with confirmation)
```
