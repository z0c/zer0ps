# psql

How to use psql client to connect to a Postgress db

## Opening connection

```
$ psql -h ${host_name}
```

## Common commands

| Command       | Description                       |
-----------------------------------------------------
| `\l`          | List databases                    |
| `\c db_name`  | Connect to database               |
| `\dt`         | Display tables in the database    |
| `\q`          | Quit                              |
