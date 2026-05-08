# ZallyMusicBot 🎵

A Telegram Music Bot built with Pyrogram and PyTgCalls.

---

## Railway Deployment Guide

### Step 1 — Required Environment Variables

Set these in Railway → Variables:

| Variable | Description |
|---|---|
| `API_ID` | From [my.telegram.org/apps](https://my.telegram.org/apps) |
| `API_HASH` | From [my.telegram.org/apps](https://my.telegram.org/apps) |
| `BOT_TOKEN` | From [@BotFather](https://t.me/BotFather) |
| `MONGO_DB_URI` | From [cloud.mongodb.com](https://cloud.mongodb.com) |
| `LOGGER_ID` | Chat ID of your log group (e.g. `-1001234567890`) |
| `OWNER_ID` | Your Telegram user ID (get from [@FallenxBot](https://t.me/FallenxBot) with `/id`) |
| `STRING_SESSION` | Pyrogram v2 session string (get from [@StringFatherBot](https://t.me/StringFatherBot)) |

### Step 2 — Setup Log Group (VERY IMPORTANT)

Before deploying, you **must** do these steps or the bot will crash:

1. Create a Telegram group (your log group)
2. Add your **bot** to the group and **promote as Admin**
3. Add your **assistant account** (STRING_SESSION account) to the group and **promote as Admin**
4. **Enable Video Chat** in the group (Group Settings → Video Chat → Start Video Chat)
5. Get the group's Chat ID using [@FallenxBot](https://t.me/FallenxBot) with `/id` and set it as `LOGGER_ID`

> ⚠️ If Video Chat is not ON in the log group, the bot will exit with an error.

### Step 3 — Optional Variables

| Variable | Default | Description |
|---|---|---|
| `STRING_SESSION2` to `STRING_SESSION5` | None | Extra assistant accounts |
| `DURATION_LIMIT` | `600` | Max song duration in minutes |
| `SPOTIFY_CLIENT_ID` | None | From [developer.spotify.com](https://developer.spotify.com/dashboard) |
| `SPOTIFY_CLIENT_SECRET` | None | From [developer.spotify.com](https://developer.spotify.com/dashboard) |
| `SUPPORT_CHANNEL` | `https://t.me/LuckyXUpdate` | Your support channel URL |
| `SUPPORT_CHAT` | `https://t.me/LuckyXSupport` | Your support group URL |

---

## Common Errors & Fixes

### `Bot has failed to access the log group/channel`
→ Bot is not admin in your log group. Add bot and promote as admin.

### `Please turn on the videochat of your log group`
→ Go to your log group → Settings → Start Video Chat.

### `Assistant client variables not defined`
→ You must set at least `STRING_SESSION`. Get it from [@StringFatherBot](https://t.me/StringFatherBot).

### `Failed to connect to your Mongo Database`
→ Check your `MONGO_DB_URI`. Make sure your MongoDB cluster allows connections from all IPs (`0.0.0.0/0`).
