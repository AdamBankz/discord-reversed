Signing Requests
----
**To avoid bots on the platform, Discord implemented custom headers to authenticate requests made to their endpoints.** <br><br>
These headers serve as cryptographic proof that the request is authentic and has not been altered, helping TikTok validate requests and protect its API from unauthorized access or tampering. We can now generate these to spoof requests made to their endpoint using this documentation.

Cookies set by Cloudflare meant to defer bots can be easily parsed through sending an initial request to discord.com and using the Set-Cookie header from the response. Another way is using a session with the code below. This will automatically use any Set-Cookies from responses.
```py
session = requests.Session()
```


<br><br>
### Security Headers:
- [X-Fingerprint](https://github.com/AdamBankz/discord-reversed/blob/main/Signing%20Requests/X-Fingerprint/README.md)
- [X-Super-Properties](https://github.com/AdamBankz/discord-reversed/blob/main/Signing%20Requests/X-Super-Properties/README.md)
