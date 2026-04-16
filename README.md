# CSEC Tracker

A free, installable web app for Caribbean secondary school students preparing for CSEC exams. Track how many past papers you've completed per subject, share your progress with friends, and stay on target for the exam season.

**Built for students in Trinidad and Tobago — works on any phone, no download required.**

---

## What It Does

CSEC Tracker helps students build a consistent past paper habit by making progress visible. The target is 15 Paper 2s per subject — the app tracks every paper logged and shows how far you are.

- Log papers by **Subject + Year + Session (January or June) + Paper 1 or 2**
- Duplicate entries are blocked automatically
- Progress bar and circular arc per subject, toward a target of 15 Paper 2s
- Paper 1s are tracked separately as a secondary stat — important, but subordinate
- Four tiers: **Starting** → **Building** → **Strong** → **Bonus Zone**

---

## Features

### Tracking
- Personalised subject list — add or remove subjects freely from a full CSEC subject list, or type your own
- Log any paper: year, session (January/June), and paper number
- Optional "Marked?" checkbox per paper — conscience feature, doesn't affect your score
- Variety badge 🌓 if you've logged both January and June sessions for a subject
- Pace indicator — "At your current pace, you'll hit 15 in ~3 weeks"

### Sharing
- **Pretty Card** — a Spotify Wrapped-style image card, generated on device, shareable to WhatsApp or Instagram Stories
  - Single subject card (1080×1080): big number, circular arc, tier badge, P1 orbs
  - Full slate card (1080×variable): all subjects in a grid
- **Paper List** — a clean text summary of every paper you've logged, shareable via WhatsApp for comparing with friends. Lets study groups coordinate which papers nobody has done yet.

### Find Past Papers
- Built-in Google search shortcuts for past papers, mark schemes, and YouTube solutions — per subject or for all subjects
- Includes a reminder to work papers under timed conditions and check the mark scheme

### Install
- **Progressive Web App (PWA)** — installs directly to your phone home screen, no App Store required
- Works offline after first visit
- Android: tap "Add to Home Screen" button in Settings
- iPhone: tap ⚙️ Settings in the app for step-by-step instructions

### Data Safety
- All data stored locally on your device (localStorage)
- **Export backup** — download your data as a JSON file and WhatsApp it to yourself
- **Import backup** — restore your data on a new phone or after clearing your browser
- No accounts, no sign-in, no server

---

## How to Use

1. Visit the app URL in your browser
2. Enter your name and pick your subjects
3. Tap any subject to open it, then log a paper
4. Tap **⚙️ Settings → Add to Home Screen** to install it like an app
5. Share your progress card with friends

---

## Files in This Repo

| File | Purpose |
|------|---------|
| `index.html` | The entire app — one self-contained file |
| `manifest.json` | PWA manifest — makes the app installable |
| `sw.js` | Service worker — enables offline use |
| `icon-192.png` | App icon (Android home screen) |
| `icon-512.png` | App icon (splash screen, high-res) |

---

## For Developers / Teachers Updating the App

The entire app lives in `index.html`. No build process, no dependencies, no framework. Open it in a browser and it runs.

**To update the app after editing:**
1. Replace `index.html` in this repo with the new version
2. Open `sw.js` and increment the cache version: `csec-tracker-v1` → `csec-tracker-v2`
3. Commit both files — GitHub Pages updates within about 60 seconds

Incrementing the service worker version forces students' phones to download the fresh version rather than serving the old cached file.

**Subject list** is defined in the `DEFAULT_SUBJECTS` constant near the top of the script section. Add or remove subjects there.

**Target** (currently 15 Paper 2s) is defined as `const TARGET = 15`. Change it in one place and the whole app updates.

---

## Design Notes

- Dark theme — deep navy/black (`#090910`) with indigo-violet gradient accents
- Spotify Wrapped aesthetic for share cards
- Tier colours: red (Starting), amber (Building), green (Strong), purple (Bonus Zone)
- Share cards generated entirely on-device using HTML Canvas — no external service
- Mobile-first, under 200KB, works on 3G

---

## Background

Built for Form 4 and 5 students sitting CSEC exams in Trinidad and Tobago. The app was designed around one core insight: students don't lack motivation as much as they lack visibility. When you can see that you've done 2 Paper 2s in Chemistry and 8 in Mathematics, you feel the gap. This app makes that gap visible — and shareable.

The Paper 2 emphasis is intentional. Paper 1 (multiple choice) is important but students gravitate toward it because it feels easier. Paper 2 (long answer, structured response) is where marks are won and lost and where most students underinvest their practice time.

---

*Made with Claude. Iterated with students in mind.*
