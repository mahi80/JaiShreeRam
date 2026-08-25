# JaiShreeRam

A LAN meeting & interview copilot. Your **Windows laptop** listens to the call
and your microphone, transcribes it, and streams AI answers to your **phone**
over your local Wi‑Fi. Answers appear on the phone — never on the laptop screen.
You bring your own AI keys; the phone needs no internet.

---

## Try it free for 10 days

Install it and it just works for **10 days** — no licence key, no card, nothing
to email. When the trial ends the app tells you your Machine ID; email that to
**kmsb80@gmail.com** for a licence key (**₹3000 / year**).

The trial runs once per machine and is tracked on our server, so reinstalling
the app does not restart it. It needs an internet connection to begin.

---

## Requirements

- A **Windows 11** laptop.
- A **phone** (Android or iPhone) on the **same Wi‑Fi** as the laptop.
- Your own **API keys** (one is free — see step 3).
- After the free trial, a **licence key** — ₹3000 / year, one machine per key.

## 1. Download & install

1. Download **`JaiShreeRam-Setup-0.1.3.exe`** from the
   [Releases](https://github.com/mahi80/JaiShreeRam/releases) page. That single
   `.exe` is the whole app — you do **not** need GitHub's auto-listed
   *Source code (zip/tar.gz)* files.
2. The app is not yet code-signed, so your browser or Windows may show a
   reputation warning on a new download (Chrome may say "virus detected",
   Windows shows SmartScreen). This is a *reputation* warning for a new,
   unsigned installer — not an actual detection. To proceed: in Chrome, click
   the download and choose **Keep**; on first run, click **More info → Run
   anyway**.
3. It installs per‑user (no admin needed) and adds a Start‑menu shortcut.

> **Already on an older version?** Please update. 0.1.0 in particular calls an AI
> model that has since been retired, so its faster answers now fail, and it has
> a licensing bug that can lock you out. Install the new version straight over
> the old one — your keys and licence carry across.

## 2. Your free trial, then a licence

**The trial starts by itself.** Launch the app and it runs for 10 days. The
panel shows how many days are left. You need to be online the first time so it
can start.

When the trial ends:

1. The app shows your **Machine ID**.
2. Email that Machine ID to **kmsb80@gmail.com** to buy a licence key
   (**₹3000 / year**). Each key activates **one machine**.
3. Paste the key into the activation screen and click **Activate**.

Each licence is valid for **1 year from activation**; after that the app stops
working until renewed. To **renew or move to a new laptop**, email
**kmsb80@gmail.com** for a new key.

## 3. Get your API keys (bring your own)

Enter these in the app's **Keys** tab, then click **Check keys and models**.

| Provider | Used for | Do you need it? | Get a key |
|---|---|---|---|
| **Groq** | speech‑to‑text, and the fastest answers | **Required** — free tier | https://console.groq.com/keys |
| **Anthropic (Claude)** | the best answers; all coding and screen solving | **Strongly recommended** — pay‑as‑you‑go | https://console.anthropic.com/settings/keys |
| **OpenAI** | a fallback so screenshots work without Claude | **Optional** — pay‑as‑you‑go | https://platform.openai.com/api-keys |

**Groq is the one you cannot skip.** It is the only speech‑to‑text, so without
it nothing is transcribed and nothing gets answered.

**Add Claude next.** It writes the best answers, and coding and screenshot
questions always go to Claude because being right matters more there than being
quick. The tested-code feature described below only works with a Claude key.

**OpenAI is optional, and most people do not need it.** It exists as a fallback:
with a Groq key alone, *spoken* questions are answered but **screenshots are
not**, because Groq has no model that can see images — an OpenAI key fills that
gap. If you already have Claude, an OpenAI key only buys a faster screenshot
answer on the *Fastest* setting.

**Saving a key:** paste it in and click **Save**. The field clears itself on
purpose — a key sitting in a text box is a key waiting to be leaked — and the
badge beside it then shows the last four characters. Clicking **Save** on an
empty field does nothing, so you cannot wipe a stored key by accident.

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

**If you change Wi‑Fi:** the pairing code is tied to the laptop's address on the
network it was on. After switching networks, generate a **fresh** pairing code —
and if the phone still won't connect, restart the app.

## 5. Pair your phone & run a session

1. Laptop → **Pair phone** → **Generate pairing code**, then scan the QR with
   the phone (valid 120 seconds, one use).
2. Laptop → **Session** tab → tick your channels → **Start session**.
3. **Answers appear on the phone.** On the phone you can also:
   - **Send** — type your own question.
   - **Answer that** — answer the other person's last question.
   - **Laptop screen** — capture the laptop screen and solve what's on it.
   - **Voice ask** — tap once to start listening on the *phone's* microphone,
     speak your question, then tap again to send it.

**Which channels to tick:** **System audio** is the important one — it captures
the other person through the call. The laptop **Microphone** is optional and is
often unavailable anyway, because apps like Teams and Zoom take exclusive hold
of it. If your own voice isn't being picked up, use **Voice ask** on the phone
instead; it is more reliable and it is what the button exists for.

**Handy hotkeys (laptop):** `Ctrl+Shift+1` capture & solve the screen ·
`Ctrl+Shift+2` hide the panel · `Ctrl+Shift+0` show it again.

## 6. Answer quality vs speed

The **Session** tab has an **Answer speed** setting:

| Setting | What it uses | Feels like |
|---|---|---|
| **Fastest** | Groq / gpt‑4o‑mini | answers start in well under a second |
| **Balanced** | gpt‑4o‑mini | about a second |
| **Best** *(default)* | Claude Opus | a few seconds, much stronger answers |
| **Most accurate** | Claude Fable at maximum reasoning | the best answer available, and clearly the slowest |

**Most accurate** is worth it for a coding problem you have screenshotted and
will sit with for a few minutes. It is *not* the setting for keeping up with
live conversation. Coding and screenshot questions always use a strong Claude
model regardless of this setting, because being right matters more there than
being quick.

## What's new in 0.1.3

- **A new app icon**, drawn for the app rather than borrowed.
- **The verify badge now tells you when it could *not* check an answer**, and
  why — Python missing, a package missing, or a language it cannot run here.
  Previously "could not check" looked exactly like "checked and passed".
- Answers are steered toward a language your laptop can actually run, so
  verification works out of the box instead of quietly skipping.
- Fixed: a blocked or missing interpreter showed a red "tests failed" over
  perfectly correct code.

## What's new in 0.1.2

- **A 10-day free trial**, so you can try the whole app before paying. It starts
  on its own, needs no key, and shows the days remaining in the panel.

## What's new in 0.1.1

- **Coding answers are checked by actually running them.** When the app writes
  code, it runs that code against its own test cases on your laptop and shows a
  badge on the phone — *running tests…*, then *✓ tests passed*. If the tests
  fail it rewrites the code and tries again, and only shows you a fix that then
  passed. A green badge means the code really ran, not that the AI thinks it
  works.
- **Voice ask** replaces the old *Phone mic* button — tap, speak, tap to send.
- **Questions are recognised by type** — coding, system design, behavioural,
  factual — and the answer is shaped to match, with the type labelled on the
  phone.
- **Most accurate** answer setting (see above).
- Many fixes, including one where the app could stop answering after you stopped
  and restarted a session, and one where a wrong system clock could lock you out
  of a valid licence.

### Optional: install Python

JavaScript answers are checked automatically — the app carries everything it
needs. **Python answers are only checked if Python is installed on your laptop.**
Without it you still get the answer, and the badge simply says *not verified*
rather than pretending.

If your interviews are Python-based and you want that checking, install Python
from **https://www.python.org/downloads/** (tick *Add python.exe to PATH* during
setup) and restart the app.

You do **not** need to install any packages. Interview answers use only the
standard library. If a particular answer does need a library, the badge names it
— install it with `pip install <name>` if you want that answer checked too.

### About running generated code

The verification above executes AI-written code **on your machine**. It runs in
a throwaway folder, is killed after a few seconds, and cannot see your API keys.
It is still code your laptop did not write, so if you would rather it did not
run at all, untick **Run & verify generated code** on the Session tab. The
feature is on by default because a coding answer that has been *tested* is worth
far more than one that merely looks right.

## Support

**kmsb80@gmail.com** — support hours **9:00 AM to 12:00 midnight IST**.

## Responsible use

This tool records a conversation that involves another person. Every connected
device shows a **recording indicator that cannot be dismissed**, and the session
records consent state. Use it only where you are **permitted and have disclosed**
that the session is being recorded — for practice, or in meetings where everyone
knows. It is not built to hide itself from anyone.
