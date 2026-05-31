## What is this? Can I eat it?

A single file header library for C++26, leveraging reflections to wrap [sqlite3](https://sqlite.org/).  
Basically, it allows to leverage plain struct types as the implicit backbone for the payload of several kinds of queries and their returned values if using `RETURNING`.  

Custom support for:

- `INSERT`
- `DELETE`
- `SELECT`
- `UPDATE`

No desire to implement a `CREATE TABLE` or `CREATE VIEW`, I don't want to fully replicate SQL.  
Otherwise one would have to handle keys, constraints, default values, multi-field keys, triggers etc.   
For my application that is all proper SQL, I only really care to remove most of the boilerplate needed to run and reuse simple queries.

The library works already, but it will need a modern C++ compiler with support for reflections, and C++26 being enabled.  
`g++16` has it behind a flag, while `clang++` only offers it in third-party branches.

It is designed to operate with exceptions disabled (but the error handling right now is very basic and should be improved.)  

Not exacly the best code I ever wrote, but it was the first time trying to get something working with reflections, and there is not much material out there, so I hope it can be helpful.

## Example

Check [this](./examples/sample.cpp) for a basic example. Ugly code, but it covers most features which have been implemented so far.

## Licence

AGPL3.0