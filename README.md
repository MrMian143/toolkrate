# ToolKrate — Free Utility Tools Website

Static site, 13 real client-side tools + About/Contact/Privacy pages. No backend, no build step — pure HTML/CSS/JS. Everything runs in the visitor's browser.

## Tools included
Word & Character Counter, Case Converter, Password Generator, QR Code Generator, BMI Calculator, Age Calculator, Percentage Calculator, Unit Converter, Color Converter, JSON Formatter, Base64 Encode/Decode, Zakat Calculator, Loan/EMI Calculator.

## Deploy to GitHub + Vercel

1. Create a new (empty) repository on GitHub.
2. Upload every file in this folder to that repo, keeping the `tools/` folder structure intact.
3. Go to vercel.com → **Add New Project** → import that GitHub repo.
4. Framework preset: **Other** (it's a plain static site — no build command needed, leave build/output settings blank).
5. Click Deploy. Vercel gives you a `yourproject.vercel.app` URL.

## Before you apply for AdSense

- Edit `contact.html` and replace the placeholder email with your real one.
- Edit `privacy-policy.html` if you add Google Analytics or any other service — mention it there.
- Consider connecting a custom domain in Vercel (Settings → Domains) — a real domain (not just `.vercel.app`) generally approves faster and looks more trustworthy to AdSense reviewers.
- Let the site sit live for a little while with real visits before applying — a brand new, empty-feeling site is more likely to get a "low value content" rejection even when every page is genuine.
- When you get your AdSense `ads.txt` snippet and ad unit codes, add the `ads.txt` file to the root of this repo, and paste your ad unit `<script>`/`<ins>` code into the `<div class="ad-slot">Ad space</div>` placeholders across the pages (search each `.html` file for `ad-slot`).

## Notes
- All 13 tools do real calculations/conversions in JavaScript — nothing is a stub or a fake result.
- The QR generator calls a free public API (`api.qrserver.com`) to render the image, since generating a QR code from scratch needs a proper QR algorithm; everything else is 100% self-contained JS.
- No localStorage/cookies are used by the tools themselves — only what an ad network you add will use.
