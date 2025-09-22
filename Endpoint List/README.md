# Important Endpoints



### `https://discord.com/api/v9/unique-username/username-suggestions-unauthed?global_name=` <br>
**Although this endpoint is supposed to suggest unused usernames, it can also be used to check whether a username is available or not.**


```py

response = requests.get("https://discord.com/api/v9/unique-username/username-suggestions-unauthed?global_name=adam")
print(response.text)
```
**The following code will return the username `adam` with 4 random integers at the end as the username `adam` is taken.**
```py
{"username":"adam0219"}
```
**If it isn't taken, then it will return the original `global_name` parameter we inserted into the URL. If `adam` was not taken, it would return this:**
```py
{"username":"adam"}
```
# 
### `https://discord.com/api/v9/auth/register` <br>
**This endpoint is used for account registration.**

### Payload:
```py
payload = {
  "fingerprint": "",
  "email": "example@gmail.com",
  "username": "adam",
  "global_name": "adam",
  "password": "password",
  "invite": "null",
  "consent": "true",
  "date_of_birth": "2000-05-05",
  "gift_code_sku_id": "null",
  "promotional_email_opt_in": "false"
}
```

### Headers:
To authenticate the request to this endpoint, you need `X-Fingerprint` and `X-Super-Properties` sent in the request, as well as `X-Fingerprint` inside of the payload. The documentation on these headers are [here.](https://github.com/AdamBankz/discord-reversed/tree/main/Signing%20Requests)

### Response:
<img width="1048" height="74" alt="image" src="https://github.com/user-attachments/assets/9701b9be-a71e-4f6f-bdac-750dbbb4757e" />  <br>
**Unfortunately, Discord is very aggressive with CAPTCHAs, instead of attempting bot detection, they push a CAPTCHA for every registration.
I was planning to reverse engineer their private mobile API on their mobile application as I believed there would be less or no CAPTCHAs there, but they use the same method over there.** ❌

# 
If a hCaptcha solver is ever released for hCaptcha Enterprise, `a9b5fb07-92ff-493f-86fe-352a2803b3df` is Discord's sitekey, which you can use for solving the CAPTCHAs and bypassing them.

