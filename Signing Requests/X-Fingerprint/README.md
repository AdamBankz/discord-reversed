# `X-Fingerprint`
The code below generates a working `x_fingerprint` header that is used to validate requests to Discord's endpoint. <br>
However, you need a `x_super_properties` header to authenticate this request. `x_super_properties` has been covered [here.](https://github.com/AdamBankz/discord-reversed/edit/main/Signing%20Requests/X-Super-Properties/README.md)
```py
def x_fingerprint():
    url = "https://discord.com/api/v9/experiments?with_guild_experiments=true"
    headers = {
        "Accept": "*/*",
        "Accept-Encoding": "gzip, deflate, br, zstd",
        "Accept-Language": "en-GB,en-US;q=0.9,en;q=0.8",
        "Connection": "keep-alive",
        "Host": "discord.com",
        "Referer": "https://discord.com/register",
        "sec-ch-ua": "\"Google Chrome\";v=\"137\", \"Chromium\";v=\"137\", \"Not/A)Brand\";v=\"24\"",
        "sec-ch-ua-mobile": "?0",
        "sec-ch-ua-platform": "\"Windows\"",
        "Sec-Fetch-Dest": "empty",
        "Sec-Fetch-Mode": "cors",
        "Sec-Fetch-Site": "same-origin",
        "User-Agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:140.0) Gecko/20100101 Firefox/140.0",
        "X-Context-Properties": "eyJsb2NhdGlvbiI6IlJlZ2lzdGVyIn0=", Base encoded JSON: {"location":"Register"}
        "X-Debug-Options": "bugReporterEnabled",
        "X-Discord-Locale": "en-GB",
        "X-Discord-Timezone": "Europe/Amsterdam",
        "X-Super-Properties": "" # Needs X-Super-Properties to authenticate the request.
    }
    resp = requests.get(url, headers=headers, timeout=10)
    return resp.json().get("fingerprint", "")
```
**Calling this function would return a value like** `1420495506810998875.TxGXYI4LolRYhaHk78HuqaVfj5w`

