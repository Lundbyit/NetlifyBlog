---
title: PostgreSQL credentials
date: 2019-11-13T20:13:30.772Z
---
When you set up postgres on your local machine in windows and you want to run psql commands from powershell or commandline you will get:

```
psql: error: could not connect to server: FATAL: database "user" does not exist
```

A way to get around that is through a database file.

**NOTE! Do not use in production**

Open explorer and type in _"%appdata%/postgresql"_ in the adress bar there you will find a pgpass.conf.

If you do not have the directory or file, create them.

There you can specify the credentials. The format is:

<hostname>:<port>:<database>:<username>:<password>

e.g

\*:5432:\*:DemoUser:DemoPassword

https://www.postgresql.org/docs/current/libpq-pgpass.html
