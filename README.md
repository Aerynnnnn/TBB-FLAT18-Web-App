# TBB / FLAT18 Web App

The **TBB Stock Take** phone app for TBB TTDI, TBB Publika and FLAT18: stock take, recipes, invoices, staff schedule, equipment and maintenance, for the **Kitchen**, **FOH** (all three outlets) and the **Bakery** (TBB TTDI).

**Open it:** https://aerynnnnn.github.io/TBB-FLAT18-Web-App/

## Install on a phone
- **Android (Chrome):** open the link, tap ⋮ → **Install app** (or **Add to Home screen**).
- **iPhone (Safari):** open the link, tap **Share** → **Add to Home Screen** → **Add**.

Open **TBB Stock Take** from the home screen, pick your section (Kitchen, FOH or Bakery) and your outlet. It is remembered; use **Switch** to change it.

## How it works
This repo only holds the app shell (section and outlet picker, icons, offline cache). Each outlet's app runs from its own
Google Apps Script deployment linked to that outlet's masterfile, so app updates reach phones without reinstalling.

## Editing the outlet list
The sections, outlets and their Apps Script links live in `content/sections.json`. You can edit them without code at
**https://aerynnnnn.github.io/TBB-FLAT18-Web-App/admin/** (Decap CMS). Log in with a GitHub account that can push to
this repo, change the list and click **Publish**. That saves a commit to `main`, and phones pick up the new list the next
time the app opens (GitHub Pages takes a minute or two to republish).

### One-time login setup
GitHub Pages can't run the GitHub login step itself, so the admin page uses Netlify's free login service:
1. In GitHub, go to **Settings → Developer settings → OAuth Apps → New OAuth App**. Use
   `https://aerynnnnn.github.io/TBB-FLAT18-Web-App/` as the homepage and `https://api.netlify.com/auth/done` as the
   callback URL. Copy the Client ID and generate a Client secret.
2. Create a free Netlify account and add a site from this repo (it doesn't need to serve the app).
3. In that Netlify site, go to **Site configuration → Access & security → OAuth → Install provider**, choose
   GitHub and paste the Client ID and secret.
4. In `admin/config.yml`, add `site_domain: <your-netlify-site>.netlify.app` under `backend:` and commit.

### Handing the app to a new owner
Add them as a collaborator on this repo (or transfer the repo) so their GitHub account can log in to the admin page.
If the repo moves, update `repo`, `site_url`, `display_url` and `logo_url` in `admin/config.yml`.
