# Journalctl

Journalctl it's the logging system used by systemd

## Reading logs by boot

You can view log boots using the `-b` switch

To view the current boot:
```$ journalctl -b
```

Navigate between boots using the `-{n}` swith where n is the number of boots to backtrack
```$ journalctl -b -1
```

To list boots
```$ journalctl --list-boots
```

## Filtering by message type

The `-p` switch filters messages by level

| int | level   |
|-----|---------|
| 0   | emerg   |
| 1   | alert   |
| 2   | crit    |
| 3   | err     |
| 4   | warning |
| 5   | notice  |
| 6   | info    |
| 7   | debug   |

The following will list all error messages of the current boot
```$ journalctl -p err -b
```

## Filtering messages by component

The `-u` switch filters the logs by a specific unit
```$ journalctl -u nginx.service
```

To get the kernel messages, use the `-k` switch
```$ journalctl -k
```
