# Tiro

**Talk anywhere on Windows, get text.** Hold **Right Ctrl**, say what you want, let go — your words appear wherever your cursor is, in any app.

Speech recognition runs **entirely on your own computer**. No audio is uploaded, there's no account, and there's nothing to pay for. After the first launch it works with the internet unplugged.

---

## Download

### [⬇ Download Tiro-Setup.exe](../../releases/latest)

Run it. No admin password needed.

Windows will show **"Windows protected your PC"** because the installer isn't code-signed — click **More info → Run anyway**. That warning appears for all independent software, not just this.

The first launch downloads the speech model once (a few hundred MB on most machines). The window tells you while it's happening.

---

## Using it

| | |
|---|---|
| **Hold Right Ctrl** | Talk, then let go. Text appears at your cursor. |
| **Double-tap Right Ctrl** | Hands-free — keep talking, tap again when done. |
| **Esc** | Throw the current dictation away. |

Closing the window doesn't quit — Tiro keeps running in the tray so the hotkey still works. **Quit Tiro** in the tray menu actually exits.

---

## Speed

| Your machine | Typical |
|---|---|
| NVIDIA graphics card | ~220 ms |
| CPU only | ~440 ms |

Both are well under a second. Tiro picks the right model for your hardware automatically — nothing to configure.

---

## Getting the best results

Open Tiro → **Words** and add names, jargon and product names you say often. This matters more than anything else: in testing, adding one company name took its error rate from 8.3% to zero.

You can also speak punctuation — "new line", "new paragraph", "question mark", "comma", "period" all become real formatting.

---

## If something doesn't work

Run this in a Command Prompt. It checks your microphone, the speech model and text insertion, then tells you which one failed in plain English:

```
"%LOCALAPPDATA%\Programs\Tiro\Tiro.exe" --selftest
```

**Nothing happens when I hold the key, or it's suddenly slow** — another app probably has Right Ctrl. The usual cause is another dictation app such as **Wispr Flow**, which can add itself back to startup when it updates and take the key before Tiro does. Your dictation then goes through that app instead, which is slower. Tiro shows a notification when it sees one running. Quit it and turn off its start-at-login setting, or uninstall it. For any other conflict, open Tiro → **General** and pick a different key.

**It types nothing** — open Tiro → **General → Test microphone**. It shows a live level bar and names the device it's using. If Windows is blocking access: **Settings → Privacy & security → Microphone**, turn on *Microphone access* and *Let desktop apps access your microphone*.

---

## Privacy

Your audio never leaves your computer. There's no account, no telemetry, and no server.

The one exception is opt-in and **off by default**: "AI polish" sends the *transcribed text* (never audio) to Anthropic's API to tidy grammar. It does nothing unless you add your own API key, and Tiro shows you exactly what it has cost.

---

## Uninstalling

Settings → Apps → Installed apps → Tiro.

Your history and settings stay in `%APPDATA%\Tiro` unless you delete that folder too.
