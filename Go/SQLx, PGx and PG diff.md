

# PG
1. I'ts under maintance right now, they recommend using the PGx driver

## Connection Pool
It's a software technique used for using already oppened db connections to make more db sql opperations.
If you've to open and close your connection to the DB every time that you had to make a db opperation, it would generate
some performance problems even on smaller projects.

And you can think "But handling a bunch of open DB connections can generate performance problems too".
Yeah, that's also true, but with pgx we can basically controls some connection parameters like idle time befor closing connection and so on.

---

## PGX | PGXPOOL

Basically, you utilize this tool (External lib) because it improves your performance related to oppening and closing db connections.

Instead of making a connection every time  a application needs to talk with de DB, generating a performance problema if you're in a large scale of calls, you can use this tool to reuse the connections from a pool.
This helps to improve application performance as opening a new connection every time can be a time consuming and resource-intensive process.
