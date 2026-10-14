# TBB / FLAT18 Web App

The **TBB Kitchen** phone app for TBB TTDI, TBB Publika and FLAT18: stock take, recipes, invoices, staff schedule, equipment and maintenance.

**Open it:** https://aerynnnnn.github.io/TBB-FLAT18-Web-App/

## Install on a phone
- **Android (Chrome):** open the link, tap ⋮ → **Install app** (or **Add to Home screen**).
- **iPhone (Safari):** open the link, tap **Share** → **Add to Home Screen** → **Add**.

Open **TBB Kitchen** from the home screen and pick your outlet. It is remembered; use **Switch outlet** to change it.

## How it works
This repo only holds the app shell (outlet picker, icons, offline cache). Each outlet's app runs from its own
Google Apps Script deployment linked to that outlet's masterfile, so app updates reach phones without reinstalling.
