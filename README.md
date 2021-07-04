# cppcheck-docker

## Introduction

Dockerfile to build latest and any tagged version of [cppcheck](https://github.com/danmar/cppcheck).

Main aims:

1. Ability to build the most recent version of [cppcheck](https://github.com/danmar/cppcheck). With this Dockerfile you can build the [lastest main](https://github.com/danmar/cppcheck/commits/main) branch.

2. Make the result image as small as possible. This Dockerfile uses [alpine linux](https://alpinelinux.org) and removes any unneeded file and strips the resulting cppcheck binary.

3. Easy to use. Only need to mount a directory to /src to start check.

## Usage

```bash
docker run -v $(pwd):/src cppcheck
```

To allow <kbd>Ctrl</kbd> + <kbd>C</kbd> during cppcheck run use `-t` docker argument:

```bash
docker run -t -v $(pwd):/src cppcheck
```

## References

[Cppcheck manual](http://cppcheck.sourceforge.net/manual.html)

## Build your own image

### Latest:
```bash
docker build -t cppcheck .
```

### For Specific version use any tag from [cppcheck tags](https://github.com/danmar/cppcheck/tags)
```bash
docker build --build-arg SOURCE_BRANCH=2.2 -t cppcheck .
```
