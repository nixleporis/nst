<!--suppress HtmlDeprecatedAttribute, CheckImageSize -->
<img src="assets/nst.svg" align="left" width="200" alt="NST logo">

NST
===

Named Specific Tag.

By Nix Leporis.

> The naming of NST is inspired by NBT (Named Binary Tag).

[中文](README-CN.md)

Objectives
----------

NST is intended to be a semantically specialized and easy-to-read configuration file format.

NST is designed to be unambiguously mappable to a hash table.

NST should be easily parsed into data structures in a variety of languages.

Example
-------

```nst
# This is NST document.

title: "EST Example"

[owner]
name: "Nix Leporis"
dob: 2000-02-04 17:58:00+08:00 # First class dates

[database]
server: "192.168.1.77"
ports: [ 2233, 2333, 3333 ]
connection_max: 5000
enabled: 1b # or true

[servers]
  # Indentation (tabs and/or spaces) is allowed but not required.
  [servers.alpha]
  ip: "10.0.0.1"
  dc: "eqdc10"

  [servers.beta]
  ip: "10.0.0.2"
  dc: "eqdc10"

[clients]
data: [ [ "gamma", "delta" ], [ 1, 2 ] ]

# Newlines are possible inside the arrays.
hosts: [
    "alpha",
    "beta"
]
```

Comparison with Other Formats
-----------------------------

NST shares characteristics with other file formats used for application configuration
and data serialization, such as TOML and YAML. Both TOML and YAML are simple and
use almost universal data types, making them easy to machine encode or decode.
Both TOML and YAML emphasize human readability features, such as comments that
make it easier to understand the purpose of a given line.
The difference of NST is that it absorbs the more obvious characteristics of the data type
of NBT format, which makes it enhance and expand a more powerful data structure while
retaining the characteristics of TOML and YAML.

Because NST is explicitly used as a configuration file format, parsing it is easy,
but it is not intended for serializing arbitrary data structures. NST always has
a hash table at the top level of the file, it can easily nest data in its tags,
but it doesn't allow top-level arrays or floats, so it can't directly serialize some data.
There is also no standard for identifying the start or end of an NST file,
which would complicate sending it over a stream.
These details must be negotiated at the application layer.

Further reading:

* TOML v1.0 spec: https://NST.io/en/v1.0.0
* YAML spec: https://yaml.org/spec/1.2.2/
* Wikipedia on NBT files: https://minecraft.fandom.com/wiki/NBT_format

Get Involved
------------

Documentation, bug reports, pull requests and all other contributions are welcome!

Wiki
----

* WIP...

Please take a look if you'd like to view or add to that list.
Thanks for being a part of the NST community!
