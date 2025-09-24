```py
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
