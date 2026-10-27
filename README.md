# Tiro

**Talk anywhere on Windows, get text.** Hold **Right Ctrl**, say what you want, let go — your words appear wherever your cursor is, in any app.

Speech recognition runs **entirely on your own computer**. No audio is uploaded, there's no account, and there's nothing to pay for. After the first launch it works with the internet unplugged.

---

## Download

### [⬇ Go to the latest release](../../releases/latest)

| File | Who it is for |
|---|---|
| **Tiro-Setup-GPU.exe** (~670 MB) | You have an NVIDIA graphics card. Includes everything the GPU needs. |
| **Tiro-Setup.exe** (~90 MB) | Everyone else. Runs on the CPU. |

Run it. No admin password needed. Already have Tiro? Run the new installer over it; your settings and history are kept.

Windows will show **"Windows protected your PC"** because the installer isn't code-signed — click **More info → Run anyway**. That warning appears for all independent software, not just this.

The first launch downloads the speech model once (a few hundred MB on most machines). The window tells you while it's happening.

---

## Using it

| | |
|---|---|
| **Hold Right Ctrl** | Talk, then let go. Text appears at your cursor. |
| **Double-tap Right Ctrl** | Hands-free — keep talking, tap again when done. |
| **Esc** | Throw the current dictation away. |

While you talk, music or video that is playing turns down and comes back when you let go. Tiro plays a quiet blip when the mic opens and closes; both are under **General** if you want them off.

Closing the window doesn't quit — Tiro keeps running in the tray so the hotkey still works. **Quit Tiro** in the tray menu actually exits.

---

## Speed

| Your machine | Typical |
|---|---|
| NVIDIA graphics card (GPU installer) | ~200 ms |
| CPU only | ~440 ms |

Both are well under a second. Tiro picks the right model for your hardware automatically — nothing to configure. If you have an NVIDIA card but installed the small installer, Tiro tells you it is running on the CPU; install the GPU one over it.

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
