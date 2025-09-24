# Intercepting requests to Discord - <img width="25" height="25" alt="image" src="https://camo.githubusercontent.com/73aa7eee091de99b1ddc7e218e3929c50c9ac24fd90248484e06b114b143b43e/68747470733a2f2f646973636f72642e636f6d2f6173736574732f66617669636f6e2e69636f" />

Intercepting requests involves capturing network traffic between the site and its endpoints, providing an overview into the sites communication and enabling the automation of every function. Typically, I'd patch the APK to disable SSL pinning, however, that won't be necessary as the request authentication on their app and website are identical. So I will just use their website to save time.


Requirements
---
- [HTTP Toolkit](https://httptoolkit.com/) - <img width="15" height="15" alt="image" src="https://github.com/user-attachments/assets/899b2278-d968-442c-a3f3-d7852b6ea8b5" />

Steps
---
1. **Launch HTTP Toolkit & select Chrome / Edge**
2. **Visit [Discord](https://discord.com/).**
   - Click important buttons (Register) (Send Message)
3. **Analyse the captcured requests in HTTP Toolkit.**

