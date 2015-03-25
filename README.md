# Docker Exec Image: Go

A Dockerfile describing an container capable of executing Go source files.

# Build

```sh
git clone https://github.com/docker-exec/go.git
docker build -t dexec/go .
```

# Usage

In a directory containing a script e.g. foo.go, run:

```sh
docker run -t --rm \
    -v $(pwd -P)/foo.go:/tmp/dexec/build/foo.go \
    dexec/go foo.go
```

## Passing arguments to the script

Arguments can be passed to the script using any of the following forms:

```
-a argument
--arg argument
--arg=argument
```

Each argument passed must be prefixed in this way, e.g.

```sh
docker run -t --rm \
    -v $(pwd -P)/foo.go:/tmp/dexec/build/foo.go \
    dexec/go foo.go \
    --arg='hello world' \
    --arg=foo \
    --arg=bar
```
