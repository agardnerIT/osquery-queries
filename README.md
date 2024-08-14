# osquery-queries
Repository of sample queries for osquery. Submissions welcomed!

## Find files across filesystem ending in .1234

```
SELECT filename, path FROM file WHERE directory LIKE '/%%' and filename LIKE '%.1234';
```
