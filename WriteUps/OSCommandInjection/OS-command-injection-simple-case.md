Lab description says `This lab contains an OS command injection vulnerability in the product stock checker` so we start testing it.

Opening Firefox Developer Tools and navigating to network tab we can see requests coming and going.

If we press check stock button a POST request with payload of `productId=2&storeId=1` will be made.

By the look of it `storeId` parameter should be supplied latter to the os command.

If we pipe the output of this command's output to the command we required to execute, we can complete this lab.

If we edit and resend request with the payload
```
productId=2&storeId=1|whoami
```
Lab will be completed.
