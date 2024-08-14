# osquery-queries
Repository of sample queries for osquery. Submissions welcomed!

## Find files across filesystem ending in .1234

```
SELECT filename, path FROM file WHERE directory LIKE '/%%' and filename LIKE '%.1234';
```

## Find files in a directory with "too permissive" permissions

```
SELECT filename, path, mode FROM file WHERE directory == '/tmp' and mode > '0644';
```
