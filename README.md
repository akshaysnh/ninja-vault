# 🥷 Ninja Vault

A ninja-guarded password vault that runs entirely in your browser. Your logins are encrypted with your master password and never leave your device. There are no servers, no accounts and no tracking.

It's a single HTML file. Open it and it works.

**[Open the live version →](https://akshaysnh.github.io/ninja-vault/)**

---

## Features

### Vault
- **Store logins:** save a name, website, username, password and notes for each one.
- **Find them fast:** search by any of those fields. Press `/` to jump to the search box.
- **One-click copy:** copy a username or password with one click. The clipboard clears itself after 30 seconds.
- **Password generator:** make passwords 8–64 characters long, with or without symbols, and see a live strength meter.
- **Auto-lock:** the vault locks itself after 5 minutes of inactivity.
- **Backups:** export an encrypted backup file and import it again later. Importing merges entries, and the newer copy wins.
- **Change your master password:** it re-encrypts everything with the new one.
- **Light and dark mode:** your choice is remembered. The first time, it follows your system setting.

### The ninja world
- **Dojo entrance:** a torii gate guarded by a ninja. Unlocking spins a combination dial and slides open paper shoji doors.
- **A living valley:** mountains, a pagoda, a river and a training dummy make up the background.
- **Seasons:** the valley follows the real date, with blossoms in spring, fireflies in summer, falling leaves in autumn and snow in winter.
- **Saving a login:** your ninja sprints in, flips onto the card and slashes a seal onto it.
- **Deleting a login:** a thief ninja drops in, hacks the record, defeats your ninja in a duel and throws the card in the bin.
- **Copying:** your ninja throws a shuriken that pins a "copied" scroll to the card. The scroll burns away when the clipboard clears.
- **Showing a password:** a ninja holds up a lantern while the password is visible, and blows it out when you hide it.
- **Searching:** a ninja runs to the matching login and bows, or shrugs when nothing matches.
- **Idle moments:**
  - Your ninja practises on the training dummy.
  - A ninja glides across the sky on a kite.
  - The thief sometimes sneaks through the valley and gets a flying kick.
- **Auto-lock:** your ninja yawns and falls asleep against the pagoda before the vault locks.
- **Backup reminder:** a messenger ninja delivers a scroll if you haven't backed up in 7 days. Tap the scroll to export.

### Security touches with ninjas
- **Rain:** it rains in the valley after wrong master passwords, and the rain gets heavier with each attempt.
- **Lockout:** on every third wrong attempt, a guard squad surrounds the gate and locks the form for 30 seconds. Refreshing the page doesn't skip the wait.
- **Heads-up:** after you unlock, you're told how many failed attempts happened while you were away.

All animations are skipped if your system has **Reduce motion** turned on.

---

## Getting started

### Use it locally
1. Download `index.html`.
2. Open it in Chrome, Edge, Firefox or Safari.
3. Choose a master password. That's it.

### Host it on GitHub Pages
1. Fork this repository, or upload `index.html` to a new public repository.
2. Go to **Settings → Pages**, set the branch to `main` and the folder to `/ (root)`, then click **Save**.
3. Your vault will be live at `https://YOUR-USERNAME.github.io/REPO-NAME/` within a minute or two.

Anyone who opens the page gets their own empty vault in their own browser. No one can see anyone else's data.

---

## How your data is protected

| What | How |
|---|---|
| Encryption | AES-256-GCM with a fresh random 12-byte IV on every save |
| Key derivation | PBKDF2-SHA256, 310,000 iterations, random 16-byte salt |
| Where data lives | Your browser's `localStorage`, encrypted |
| Network | A Content Security Policy blocks all outgoing requests except Google Fonts |
| Clipboard | Cleared 30 seconds after copying |
| Idle | Auto-locks after 5 minutes; the key is wiped from memory |
| Guessing | 30-second lockout after every 3 wrong attempts |

The master password itself is never stored. A few harmless settings are kept unencrypted: your theme, the failed-attempt count, the lockout timer and the date of your last backup.

---

## ⚠️ Important

- **A forgotten master password can't be recovered.** There's no reset and no back door. That's what keeps the vault secure.
- **Your data lives in one browser on one device.** Clearing browser data, using a private window or switching browsers means starting with an empty vault. **Export backups regularly.**
- **Each web address gets its own vault.** The local file and the GitHub Pages version store data separately. Use export and import to move logins between them.
- **Never commit backup files to a public repository.** They're encrypted, but anyone could download them and try to guess your password. Keep them on your own devices or in private cloud storage.
- **This is a personal project and has not been independently security-audited.** For your most important accounts, such as banking or your main email, consider an established password manager like Bitwarden or 1Password.

---

## Tech

- **Code:** one self-contained `index.html` written in vanilla HTML, CSS and JavaScript, with no frameworks and no build step.
- **Encryption:** the browser's built-in Web Crypto API.
- **Artwork and animation:** all graphics are hand-drawn inline SVG. Animations use CSS and the Web Animations API.
- **Fonts:** Bricolage Grotesque, Instrument Sans and JetBrains Mono, loaded from Google Fonts. If they can't load, the page falls back to system fonts.

---

## Keyboard shortcuts

| Key | Action |
|---|---|
| `/` | Focus search |
| `Esc` | Close a dialog |
| Click during the delete scene | Skip the animation |

---
