<div align="center">
< Aminul Remake Facebook Chat API >

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


# 📥 Installation

```bash
npm install aminul-remake-fca@latest

```
# 🚀 Example Usage

const login = require("aminul-remake-fca");

// Simple echo bot
login({ appState: [] }, (err, api) => {
    if (err) return console.error(err);

    api.listenMqtt((err, event) => {
        if (err) return console.error(err);

        api.sendMessage(event.body, event.threadID);
    });
});



const fs = require("fs");
const login = require("aminul-remake-fca");

login({ appState: [] }, (err, api) => {
    if (err) return console.error(err);

    api.sendMessage({
        body: "Here’s an image 📸",
        attachment: fs.createReadStream(__dirname + "/image.jpg")
    }, "000000000000000");
});

# 💬 Sending Messages

api.sendMessage(message, threadID[, callback][, messageID])

Supported types:

Text → { body: "Hello World" }

Sticker → { sticker: "STICKER_ID" }

Image/File → { attachment: fs.createReadStream("file.jpg") }

URL Preview → { url: "https://example.com" }

Emoji → { emoji: "😂", emojiSize: "large" }


# 📌 Example: Text

const login = require("aminul-remake-fca");

login({ appState: [] }, (err, api) => {
    if (err) return console.error(err);

    api.sendMessage("Hello ✨", "000000000000000");
});

# 🔐 Saving Session (AppState)

To avoid logging in every time:

const fs = require("fs");
const login = require("aminul-remake-fca");

login({ appState: [] }, (err, api) => {
    if (err) return console.error(err);

    fs.writeFileSync("appstate.json", JSON.stringify(api.getAppState()));
});

# 👂 Listening to Events

const fs = require("fs");
const login = require("aminul-remake-fca");

login({ appState: JSON.parse(fs.readFileSync("appstate.json", "utf8")) }, (err, api) => {
    if (err) return console.error(err);

    api.setOptions({ listenEvents: true });

    var stopListening = api.listenMqtt((err, event) => {
        if (err) return console.error(err);

        switch (event.type) {
            case "message":
                if (event.body === "/stop") {
                    api.sendMessage("👋 Goodbye!", event.threadID);
                    return stopListening();
                }
                api.sendMessage("EchoBot: " + event.body, event.threadID);
                break;
            case "event":
                console.log(event);
                break;
        }
    });
});


# 📚 Projects Using Aminul Remake FCA

🟢 Miraiv2

🟢 GoatBot

🟢 [Autobot / Mirai Mods]

🟢 Any custom modular bot frameworks
🔐 Saving Session (AppState)

To avoid logging in every time:

 # 🔗 Repository

## 📦 NPM
```bash
npm i aminul-remake-fca

```

---

✨ Made with ❤️ by Aminul Sordar
