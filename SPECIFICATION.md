Sqon
====

Introduction
------------

Sqon, pronounced "[scone][]" (/ˈskɒn/), is a package file format for PHP. It is designed to package an entire application as a single PHP script.

[scone]: https://en.wikipedia.org/wiki/Scone

### Helpful Hints

- Sqon is a portmanteau of "SQLite container".
- A "sqon" is a file that conforms to this specification.
- A sqon file may optionally use the `.sqon` suffix.

File Format
-----------

The package file format consists of four major components:

1. The bootstrap script.
2. The SQLite database.
3. The file signature.
4. The binary packed values.

### Layout

The data in the sqon file are arranged in the following order:

| Bytes | [Pack][] |Description                              |
|:------|:---------|:----------------------------------------|
| ?     | -        | The bootstrap script.                   |
| ?     | -        | The SQLite database.                    |
| ?     | -        | The signature of the file.              |
| `4`   | `l`      | The offset of the file signature.       |
| `4`   | `l`      | The offset of the SQLite database.      |
| `4`   | `l`      | The size of the bootstrap script.       |
| `4`   | `l`      | The size of the file signature.         |
| `4`   | `l`      | The size of the SQLite database.        |
| `4`   | `l`      | The algorithm for the file signature.   |

[Pack]: http://php.net/pack

File Contents
-------------

### Bootstrap Script

The bootstrap script consists of up to three parts:

1. The [shebang line][].
2. The self extracting script.
3. The "halt compiler" invocation.

[shebang line]: https://en.wikipedia.org/wiki/Shebang_(Unix)

#### Shebang Line

The shebang line is optional but is recommended for applications that are intended to be executed from the command line. The default shebang line is:

    #!/usr/bin/env php

> The shebang line is followed by the line feed character ("\n", or ASCII `0xA`).

This shebang line will allow users to change their environment to use a PHP interpeter other than their system default in order to run the application. It is also recommended that no additional options be passed in the shebang line as it may introduce [portability issues][].

[portability issues]: https://en.wikipedia.org/wiki/Shebang_(Unix)#Portability

#### Self Extracting Script

TBD

#### Halt Compiler Invocation

TBD

### SQLite Database

TBD

### File Signature

TBD

### Binary Packed Values

TBD
