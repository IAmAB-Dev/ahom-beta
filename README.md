# Ahom — private email, on your device

**A local-first, privacy-first desktop email client.** Your mail lives
encrypted on *your* machine — not on someone else's server — with on-device
AI that never sends your email to the cloud.

Made by **Plenith LLC**. This repository hosts the **public beta** for Windows.

> ⚠️ **This is beta software.** Things may break and features are still
> landing. Please don't make it your only mail client yet — and tell us what
> you find (see **Feedback** below). Thank you for testing!

---

## ⬇️ Download

Grab **`Ahom_0.1.0_x64-setup.exe`** from the **[latest release](../../releases/latest)**.

**Windows 10 / 11, 64-bit.**

### Installing
1. Run the downloaded `Ahom_0.1.0_x64-setup.exe`.
2. It's **code-signed by Plenith LLC.** Until the certificate builds up
   download reputation, Windows SmartScreen may still show a blue "Windows
   protected your PC" screen — if it does, click **More info → Run anyway.**
   (You can confirm it's genuine: right-click the file → **Properties →
   Digital Signatures** → you should see **Plenith LLC**.)
3. It installs **per-user — no administrator prompt** — in a few seconds, and
   installs cleanly over a previous version.

---

## What it does

- **Local-first & encrypted.** Your messages, attachments, and search index
  are stored in an encrypted database *on your device* (SQLCipher). There is
  no "Ahom cloud" holding your mail.
- **Your accounts, together.** Connect **Gmail**, **iCloud**, **Yahoo**,
  **Fastmail**, and other IMAP providers — several at once, each colour-coded.
- **On-device AI.** Summarize a thread, ask a question about a message, or
  get a smart reply — it all runs **locally** on your machine. Your email is
  never sent to a cloud AI service.
- **Smart triage.** Mail is sorted into buckets (Priority · Personal ·
  Newsletters · Watch · Quiet …) by an on-device classifier that learns from
  your corrections.
- **Security built in.** Phishing detection, sender authentication
  (DMARC + BIMI verified-sender logos), tracking-pixel blocking, remote-image
  gating, and PGP encrypt / decrypt.
- **A clean reader.** Faithful rendering of formatted mail, inline **preview**
  of PDF / image / text attachments, and a typeset **Print / Save-as-PDF.**
- **The rest of an inbox:** calendar & contacts, meeting invites, snooze,
  send-later, unsubscribe, search.

---

## Connecting an account

Ahom talks **straight to your email provider** over IMAP/SMTP — there's no
Ahom server in between. For this beta you connect using an **app password**: a
one-time code your provider generates for third-party apps like Ahom. It's the
same method Apple Mail and Thunderbird use, and the important part for you is
that **you can set it all up yourself — no invite, no waiting on anyone.**

> **Why an app password instead of my normal password?** When you have
> two-factor authentication turned on (and you should), providers hand out a
> separate, revocable password for individual apps. It only works for mail,
> you can revoke it any time from your provider's website, and Ahom keeps it
> in your operating system's encrypted keychain — never in plain text, and
> never on any server of ours.

**Where to add an account**
- **First launch:** the welcome screen walks you through it — click
  **Continue** past the privacy screen to reach the provider grid.
- **Any time after that (or to add a second account):** click the **⊕** at
  the bottom of the left rail, or go to **Settings → Accounts → Add account.**

Both routes open the same "Connect an account" screen described below.

---

### 📩 Gmail  — use the **"Other provider"** option

Gmail connects with a Google **App Password**, which first needs **2-Step
Verification** switched on.

1. **Turn on 2-Step Verification** (skip if you already have it):
   [myaccount.google.com/security](https://myaccount.google.com/security) →
   **2-Step Verification** → follow the prompts.
2. **Create the App Password:** open
   [myaccount.google.com/apppasswords](https://myaccount.google.com/apppasswords),
   type a name like **Ahom**, and click **Create.** Google shows a
   **16-character** password (four blocks of four letters). Copy it.
3. In Ahom's connect screen, click the slim **"Other provider"** row (labelled
   **IMAP / SMTP**) *underneath* the four tiles.

   > ⚠️ **Don't click the big "Gmail" tile.** That tile is Google's one-click
   > sign-in, which is **limited to a pre-approved list during the beta** and
   > will fail with *"access denied."* The **"Other provider"** row uses your
   > app password and works for **any** Gmail account.

4. Type your full **Gmail address.** A **Server settings** panel opens
   automatically — fill it in **exactly** like this:

   | Field       | Value             |
   |-------------|-------------------|
   | IMAP host   | `imap.gmail.com`  |
   | IMAP port   | `993`             |
   | SMTP host   | `smtp.gmail.com`  |
   | SMTP port   | `587`             |

5. In the **password** field, paste the **16-character app password** from
   step 2 (with or without the spaces — both work).
6. Click **Sign in.** Ahom checks the login and starts syncing.

> **Google Workspace / work or school Gmail?** Your admin has to allow App
> Passwords, and IMAP has to be enabled. If step 2 shows no "App passwords"
> option, your admin has turned it off — use a personal Gmail or an iCloud
> account for the beta instead.

---

### ☁️ iCloud  — the easy one (email + app password, servers auto-fill)

1. Make sure **two-factor authentication** is on for your Apple ID (required
   for the next step).
2. Generate an **app-specific password:**
   [appleid.apple.com](https://appleid.apple.com) → **Sign-In & Security →
   App-Specific Passwords → +** → name it **Ahom.** You'll get a password that
   looks like `abcd-efgh-ijkl-mnop`.
3. In Ahom, click the **iCloud** tile.
4. Enter your **@icloud.com** (or **@me.com** / **@mac.com**) address and paste
   the app-specific password. **No server settings needed** — Ahom fills them
   in for you.
5. Click **Sign in.**

---

### 📮 Yahoo · Fastmail · GMX · Zoho  — also automatic

Just like iCloud: click the matching tile (or **Other provider**), enter your
email and that provider's **app password**, and Ahom auto-fills the servers.
Generate the app password in the provider's security settings — for example:

- **Fastmail:** Settings → **Privacy & Security → App Passwords → New.**
- **Yahoo:** Account Security → **Generate app password.**
- **Zoho / GMX:** Security / IMAP settings → **Application-specific password.**

---

### 📧 Outlook · Hotmail · Live · Microsoft 365

Microsoft turned off app-password IMAP for personal Outlook accounts, so Ahom
uses **Microsoft's own sign-in** instead. Click the **Outlook** tile and
finish in the Microsoft window that opens — no app password needed.

> If Microsoft stops at a consent or verification screen, that account isn't
> cleared for the beta yet. Use a **Gmail** or **iCloud** account for now and
> let whoever invited you know.

---

### 🛟 If a connection fails

- **"Authentication failed" / "LOGIN failed"** — you're almost certainly using
  your *normal* password. Go back, generate an **app password** (steps above),
  and paste that instead.
- **Gmail won't connect** — confirm **2-Step Verification is on** (App
  Passwords don't exist without it) and that you typed `imap.gmail.com` and
  `smtp.gmail.com` exactly. If it signs in but no mail appears, open Gmail on
  the web → **Settings → See all settings → Forwarding and POP/IMAP → Enable
  IMAP → Save**, then try again.
- **iCloud says your password won't work** — that message means *use an
  app-specific password* from appleid.apple.com, not your Apple-ID login.
- **Still stuck?** See **Feedback** below — a screenshot and which provider
  you used helps a lot.

---

## What to try

- Connect an account, let it sync, and see how it sorts your mail into buckets.
- Open a formatted email, a newsletter, and a receipt — does everything render
  cleanly and consistently?
- Open a **PDF or image attachment** — it should preview *inside* the app.
- **Print** an email — `⋯` menu → **Print / Save as PDF**, or press **Ctrl+P.**
- Try the AI: **Summarize** a long thread, or **Ask** a question about a message.
- Compose and send; try a **Smart reply.**

## Known beta limitations
- Attachment handling / rendering for some providers is still being hardened.
- The one-click **"Gmail"** tile and the **Microsoft** sign-in button are
  invite-only during the beta. **This doesn't limit you** — connect Gmail with
  an app password via **"Other provider"** (see *Connecting an account*), and
  iCloud / Yahoo / Fastmail / GMX / Zoho have no such limit at all.
- Only **Windows** is published for now — macOS / Linux builds aren't out yet.

---

## 💬 Feedback

Found a bug or have an idea? Either:
- **[Open an issue](../../issues/new)** on this repo (needs a GitHub account), or
- **reply to whoever shared this link** with you.

A screenshot and which provider you connected (Gmail / iCloud / Yahoo / …) help
a lot — plus what you did, what you expected, and what actually happened.

---

## Privacy, in one paragraph

Ahom talks to **your email provider**, and (optionally, once) downloads a
local AI model — that's it. There is no backend of ours for it to phone home
to. Your mail, its search index, and the AI all stay on your device. The full
privacy statement ships inside the app.

---

*Ahom is a product of **Plenith LLC.** Public beta build — © 2026 Plenith LLC.*
