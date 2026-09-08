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
- **Your accounts, together.** Connect **Gmail**, **Outlook / Microsoft
  365**, and **iCloud / IMAP** — several at once, each colour-coded.
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

- **iCloud / IMAP** — use an **app-specific password**, not your normal
  password. For iCloud, generate one at
  [appleid.apple.com](https://appleid.apple.com) → **Sign-In & Security →
  App-Specific Passwords.** Works out of the box.
- **Gmail / Outlook** — sign-in uses OAuth, and **during the beta it's
  limited to approved testers.** If you want to test with a Gmail or Outlook
  account, send that email address to whoever invited you so it can be
  added to the tester list. (iCloud / IMAP needs no such step.)

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
- Gmail & Outlook sign-in is tester-limited during the beta (see above).
- Only **Windows** is published for now — macOS / Linux builds aren't out yet.

---

## 💬 Feedback

Found a bug or have an idea? Either:
- **[Open an issue](../../issues/new)** on this repo (needs a GitHub account), or
- **reply to whoever shared this link** with you.

A screenshot and which account type you used (Gmail / Outlook / iCloud) help a lot.

---

## Privacy, in one paragraph

Ahom talks to **your email provider**, and (optionally, once) downloads a
local AI model — that's it. There is no backend of ours for it to phone home
to. Your mail, its search index, and the AI all stay on your device. The full
privacy statement ships inside the app.

---

*Ahom is a product of **Plenith LLC.** Public beta build — © 2026 Plenith LLC.*
