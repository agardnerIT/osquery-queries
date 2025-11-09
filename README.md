# osquery-queries
Repository of sample queries for osquery. Submissions welcomed!

## Log in to interactive mode

```
osqueryi
```

## Exit interactive mode

```
.exit
```

## See all available data (represented as tables)

```
.tables
```

## See the table layout for the `uptime` table

```
.schema uptime
```

## View system uptime

```
select * from uptime;
```

## Find files across filesystem ending in .1234

```
SELECT filename, path FROM file WHERE directory LIKE '/%%' and filename LIKE '%.1234';
```

## Find files in a directory with "too permissive" permissions

```
SELECT filename, path, mode FROM file WHERE directory == '/tmp' and mode > '0644';
```

## Find files in a directory bigger than X bytes

```
SELECT filename, path, mode, size FROM file WHERE directory == '/tmp' and size > 5;
```

## See all non Apple Apps installed on MacOS

```
select name from apps where bundle_identifier NOT LIKE 'com.apple.%%';
```

## Get battery percentage

```
select percent_remaining from battery;
```

## Which packages are installed by homebrew and at which versions?

```
select * from homebrew_packages;
```

## View non Apple kernel extensions

```
select * from kernel_extensions where name NOT LIKE 'com.apple%';
```

## How much RAM and what type is in the system?

```
select memory_type, size from memory_devices;
```

## Get system time

```
select * from time;
```

## Find the process ID using a particular port
Equivalent to `lsof -i :8888`

```
SELECT p.pid AS process_id, lp.port AS port FROM listening_ports lp JOIN processes p ON lp.pid = p.pid WHERE lp.port = 8888;
```
