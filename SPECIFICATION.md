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
| `4`   | `i`      | The offset of the file signature.       |
| `4`   | `i`      | The offset of the SQLite database.      |
| `4`   | `i`      | The size of the bootstrap script.       |
| `4`   | `i`      | The size of the file signature.         |
| `4`   | `i`      | The size of the SQLite database.        |
| `4`   | `i`      | The algorithm for the file signature.   |

[Pack]: http://php.net/pack

File Contents
-------------

### Bootstrap Script

TBD

### SQLite Database

TBD

### File Signature

TBD

### Binary Packed Values

TBD
