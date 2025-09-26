<div align="center">

![Banner](https://i.imgur.com/QpqujSt.jpeg)

<h2 align="center"><b>Aminul Remake Facebook Chat API</b></h2><br>
This package is proudly recreated and maintained by <b>Aminul Sordar</b> ✨

![Preview](https://i.imgur.com/nFCeYmQ.jpeg)

_Disclaimer_: We are not responsible if your account gets banned for spammy activities such as:  
🚫 Sending too many messages to strangers  
🚫 Sending spammy links  
🚫 Logging in/out too quickly  
🚫 Any suspicious automated behavior  

⚠️ Be a responsible Facebook user and bot developer.

---

# 🎉 Features

- ✅ Automatic **AppState relogin** when errors are detected.  
- ✅ Handles **forced logout** and re-prompts for new session.  
- ✅ Detects **locked/suspended accounts** and displays reason.  
- ✅ Provides powerful helper functions:  
  - `api.relogin()`  
  - `api.stopListenMqtt()`  
  - `api.getRegion()`  
  - `api.setProfileGuard()`  
  - `api.addFunctions()`  
  - `api.getBotInitialData()`  
- ✅ **Automatic refresh** of `fb_dtsg` tokens every midnight (GMT+8).  
- ✅ **Experimental features:**  
  - Random user-agent rotation  
  - Bypass region options (`PRN`, `PNB`, `HKG`, `SYD`, etc.)  
- ✅ Optimized user-agent = less frequent logouts.  
- ✅ Tested with **Mirai, GoatBot, Autobot** style frameworks.

---

# 📥 Installation

```bash
npm install aminul-remake-fca@latest
