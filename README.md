# JaiShreeRam

A LAN meeting & interview copilot. Your **Windows laptop** listens to the call
and your microphone, transcribes it, and streams AI answers to your **phone**
over your local Wi‑Fi. Answers appear on the phone — never on the laptop screen.
You bring your own AI keys; the phone needs no internet.

---

## Requirements

- A **Windows 11** laptop.
- A **phone** (Android or iPhone) on the **same Wi‑Fi** as the laptop.
- Your own **API keys** (one is free — see step 3).
- A **licence key** — ₹3000 / year, one machine per key (see step 2).

## 1. Download & install

1. Download **`JaiShreeRam-Setup-0.1.0.exe`** from the
   [Releases](https://github.com/mahi80/JaiShreeRam/releases) page. That single
   `.exe` is the whole app — you do **not** need GitHub's auto-listed
   *Source code (zip/tar.gz)* files.
   **Mirror:** if your browser blocks the GitHub download, get the same file
   from [Google Drive](https://drive.google.com/file/d/1UxCERA3OpgqPTmi9Hf5smEwmNlLUzkY6/view).
2. The app is not yet code-signed, so your browser or Windows may show a
   reputation warning on a new download (Chrome may say "virus detected",
   Windows shows SmartScreen). This is a *reputation* warning for a new,
   unsigned installer — not an actual detection. To proceed: in Chrome, click
   the download and choose **Keep**; on first run, click **More info → Run
   anyway**.
3. It installs per‑user (no admin needed) and adds a Start‑menu shortcut.

## 2. Activate your licence

1. On first launch the app shows your **Machine ID**.
2. Email that Machine ID to **kmsb80@gmail.com** to buy a licence key
   (**₹3000 / year**). Each key activates **one machine**.
3. Paste the key into the activation screen and click **Activate**.

Each licence is valid for **1 year from activation**; after that the app stops
working until renewed. To **renew or move to a new laptop**, email
**kmsb80@gmail.com** for a new key.

## 3. Get your API keys (bring your own)

Enter these in the app's **Keys** tab, then click **Check keys and models**.

| Provider | Used for | Cost | Get a key |
|---|---|---|---|
| **Groq** | speech‑to‑text + fast answers | **Free tier** | https://console.groq.com/keys |
| **Anthropic (Claude)** | best answers + screen solving | pay‑as‑you‑go | https://console.anthropic.com/settings/keys |
| **OpenAI** | fast screenshot answers (optional) | pay‑as‑you‑go | https://platform.openai.com/api-keys |

Groq alone is enough to start. Add Claude for the best answers and screenshot
solving.

## 4. First‑time phone setup (install the certificate — once)

Phone browsers only allow the microphone and camera on a **trusted secure**
connection, so you install the app's local certificate once.

1. On the phone, open **`http://<laptop-ip>:18080`** (the laptop shows its
   address on the **Pair phone** tab) and tap **Download certificate**.
2. **Android:** Settings → Security & privacy → More security settings →
   Encryption & credentials → **Install a certificate → CA certificate** → pick
   the downloaded file. *(Android needs a screen lock/PIN set first.)*
3. **iPhone:** after downloading, install the profile in Settings → General →
   **VPN & Device Management**, then — the step people miss — Settings → General
   → About → **Certificate Trust Settings** and turn **full trust** on for it.

**Same‑Wi‑Fi note:** the laptop and phone must be on the **same network**. If
they won't connect, your Wi‑Fi may block device‑to‑device traffic — use a phone
hotspot instead, and connect the laptop to it.

## 5. Pair your phone & run a session

1. Laptop → **Pair phone** → **Generate pairing code**, then scan the QR with
   the phone (valid 120 seconds, one use).
2. Laptop → **Session** tab → tick your channels → **Start session**.
3. **Answers appear on the phone.** On the phone you can also:
   - **Send** — type your own question.
   - **Answer that** — answer the other person's last question.
   - **Laptop screen** — capture the laptop screen and solve what's on it.
   - **Phone mic** — use the phone as the microphone.

**Handy hotkeys (laptop):** `Ctrl+Shift+1` capture & solve the screen ·
`Ctrl+Shift+2` hide the panel · `Ctrl+Shift+0` show it again.

## Support

**kmsb80@gmail.com** — support hours **9:00 AM to 12:00 midnight IST**.

## Responsible use

This tool records a conversation that involves another person. Every connected
device shows a **recording indicator that cannot be dismissed**, and the session
records consent state. Use it only where you are **permitted and have disclosed**
that the session is being recorded — for practice, or in meetings where everyone
knows. It is not built to hide itself from anyone.
