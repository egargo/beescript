# BeeScript

:bee: BeeScript, a language that compiles to C.


## About

BeeScript, a language that compiles to C.

This project has no real world usage other than to learn how to create a
custom lexer and AST (Abstract Syntax Tree). The implementation is written in
Python as I wanted to do a quick-and-dirty proof-of-concept project.
I might even re-write the whole thing.

Currently, the language (if you can call it that) only supports writing to
stdout and creating variables and assigning values to it.

This project is inspired by
[MoonScript](https://moonscript.org/),
[Monkey Lang](https://monkeylang.org/),
and [Bato](https://github.com/jjuliano/bato).


> [!NOTE]
> This is a project I hacked together in three days, expect the code to be messy.


## Dependencies

- Python 3.10 or higher
- GCC


## Usage

```sh
git clone https://github.com/egargo/beescript.git

cd beescript

./beescript main.bee

gcc main.c && ./a.out
```


## Syntax

The following BeeScript program:

```py
# This is a BeesCript program

print "Hello, world!"

print 12

A = 65
Z = 90

a = 97
z = 122

greeting = "Hello, World!"

print A
print Z

print a
print z

print greeting
```

compiles to the following C program:

```c
#include <stdio.h>

int main() {
	printf("%s\n", "Hello, world!");
	printf("%d\n", 12);
	int A = 65;
	int Z = 90;
	int a = 97;
	int z = 122;
	char greeting[] = "Hello, World!";
	printf("%d\n", Z);
	printf("%d\n", z);
	return 0;
}
```
