# ToolKrate — Free Utility Tools Website

Static site, 20 real client-side tools + About/Contact/Privacy pages. No backend server — pure HTML/CSS/JS (a few tools load a small, well-known JS library from cdnjs for PDF/zip work, listed below). Black-and-red theme with glowing buttons and cards. All processing happens in the visitor's browser.

## Tools included

**Text & writing:** Word/Character Counter, Case Converter, JSON Formatter, Base64 Encode/Decode
**Calculators:** BMI, Age, Percentage, Loan/EMI, Zakat, Unit Converter
**Generators & utilities:** Password Generator, QR Code Generator, Color Converter
**File & image tools:** Image Compressor, Image Resizer, Image Converter (PNG/JPG/WebP), Images to PDF, Merge PDF, Word (.docx) to PDF, Zip Files

## Deploy to GitHub + Vercel

1. Create a new (empty) repository on GitHub.
2. Upload every file in this folder to that repo, keeping the `tools/` folder structure intact.
3. Go to vercel.com → **Add New Project** → import that GitHub repo.
4. Framework preset: **Other** (plain static site — no build command needed, leave build/output settings blank).
5. Click Deploy. Vercel gives you a `yourproject.vercel.app` URL.

## Before you apply for AdSense

- Contact page is already set to zaidsarwar1403@gmail.com.
- Let the site sit live for a little while with real visits before applying.
- Consider a custom domain in Vercel (Settings → Domains) — helps approval and trust.
- When you get your AdSense `ads.txt` snippet and ad unit codes, add `ads.txt` to the repo root, and paste your ad unit code into the `<div class="ad-slot">Ad space</div>` placeholders (search each `.html` file for `ad-slot`).

## About the file/image tools

- **Image Compressor, Image Resizer, Image Converter** — pure JavaScript using the browser's Canvas API. No external library.
- **Images to PDF, Merge PDF** — use [pdf-lib](https://pdf-lib.js.org/) (MIT license), loaded from cdnjs.
- **Word to PDF** — uses [mammoth.js](https://github.com/mwilliamson/mammoth.js) to read the .docx and [html2pdf.js](https://github.com/eKoopmans/html2pdf.js) to render it to PDF, both from cdnjs. Works well for normal documents (headings, paragraphs, lists, simple tables); very complex layouts may not carry over exactly — this is stated on the page itself.
- **Zip Files** — uses [JSZip](https://stuk.github.io/jszip/) (MIT license), loaded from cdnjs.

All of these libraries are free, open-source and widely used — no fees, no accounts, no API keys needed. They only run in the visitor's browser; nothing is uploaded anywhere.

## Notes
- Colors, glow and every visual style live in `style.css` under `:root` — change `--signal` (red), `--paper` (background) and `--ink` (text) there to retint the whole site later.
- Requires an internet connection for the tools that load a CDN library (Images to PDF, Merge PDF, Word to PDF, Zip Files) and for the QR generator (calls a free public API). Every other tool works fully offline once the page has loaded.
