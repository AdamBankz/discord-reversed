# `X-Super-Properties`
The code below generates a working `x-super-properties` header that is used to validate requests to Discord's endpoint. <br>

```py
import uuid

def x_super_properties():
    props = {
        "os": "Windows",
        "browser": "Chrome",
        "device": "",
        "system_locale": "en-GB",
        "has_client_mods": False,
        "browser_user_agent": (
            "Mozilla/5.0 (Windows NT 10.0; Win64; x64)"
            "AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36"
        ),
        "browser_version": "120.0",
        "os_version": "10",
        "referrer": "",
        "referring_domain": "",
        "referrer_current": "",
        "referring_domain_current": "",
        "release_channel": "stable",
        "client_build_number": random.randint(400_000, 500_000),
        "client_event_source": None,
        "client_launch_id": str(uuid.uuid4()),
        "client_app_state": "unfocused"
    }
    compact = json.dumps(props, separators=(",", ":")).encode("utf-8")
    return base64.b64encode(compact).decode("utf-8")
```


**Calling this function would return an encoded JSON browser fingerprint like:** 
```
eyJvcyI6IldpbmRvd3MiLCJicm93c2VyIjoiQ2hyb21lIiwiZGV2aWNlIjoiIiwic3lzdGVtX2xvY2FsZSI6ImVuLUdCIiwiaGFzX2NsaWVudF9tb2RzIjpmYWxzZSwiYnJvd3Nlcl91c2VyX2FnZW50IjoiTW96aWxsYS81LjAgKFdpbmRvd3MgTlQgMTAuMDsgV2luNjQ7IHg2NClBcHBsZVdlYktpdC81MzcuMzYgKEtIVE1MLCBsaWtlIEdlY2tvKSBDaHJvbWUvMTIwLjAuMC4wIFNhZmFyaS81MzcuMzYiLCJicm93c2VyX3ZlcnNpb24iOiIxMjAuMCIsIm9zX3ZlcnNpb24iOiIxMCIsInJlZmVycmVyIjoiIiwicmVmZXJyaW5nX2RvbWFpbiI6IiIsInJlZmVycmVyX2N1cnJlbnQiOiIiLCJyZWZlcnJpbmdfZG9tYWluX2N1cnJlbnQiOiIiLCJyZWxlYXNlX2NoYW5uZWwiOiJzdGFibGUiLCJjbGllbnRfYnVpbGRfbnVtYmVyIjo0NTE0MDgsImNsaWVudF9ldmVudF9zb3VyY2UiOm51bGwsImNsaWVudF9sYXVuY2hfaWQiOiI3YmE0YWIxYS05ZDMxLTQyN2QtOTc5Ni00ZTQxM2VkOTgwMjQiLCJjbGllbnRfYXBwX3N0YXRlIjoidW5mb2N1c2VkIn0=
```

**When decoded, the string turns to:**
```py
{"os":"Windows","browser":"Chrome","device":"","system_locale":"en-GB","has_client_mods":false,"browser_user_agent":"Mozilla/5.0 (Windows NT 10.0; Win64; x64)AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36","browser_version":"120.0","os_version":"10","referrer":"","referring_domain":"","referrer_current":"","referring_domain_current":"","release_channel":"stable","client_build_number":451408,"client_event_source":null,"client_launch_id":"7ba4ab1a-9d31-427d-9796-4e413ed98024","client_app_state":"unfocused"}
```

