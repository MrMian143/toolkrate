# ToolKrate — Free Utility Tools Website

Static site, 22 real client-side tools + About/Contact/Privacy pages. No backend server — pure HTML/CSS/JS (a few tools load a small, well-known JS library from a CDN for PDF/video/zip work, listed below). Black-and-red theme with glowing buttons and cards. All processing happens in the visitor's browser.

## Tools included

**Text & writing:** Word/Character Counter, Case Converter, JSON Formatter, Base64 Encode/Decode
**Calculators:** BMI, Age, Percentage, Loan/EMI, Zakat, Unit Converter
**Generators & utilities:** Password Generator, QR Code Generator, Color Converter
**File & image tools:** Image Compressor, Image Resizer, Image Converter (PNG/JPG/WebP), Images to PDF, Merge PDF, Word (.docx) to PDF, Zip Files, Video Compressor, PDF Compressor

## Deploy to GitHub + Vercel

1. Create a new (empty) repository on GitHub.
2. Upload every file in this folder to that repo, keeping the `tools/` folder structure intact.
3. Go to vercel.com → **Add New Project** → import that GitHub repo.
4. Framework preset: **Other** (plain static site — no build command needed, leave build/output settings blank).
5. Click Deploy.

This package also includes `sitemap.xml` and `robots.txt`, already pointed at `https://toolkrate.vercel.app` — upload both to the repo root along with everything else, and the Google-site-verification meta tag is already in `index.html`.

## Before you apply for AdSense

- Contact page is already set to zaidsarwar1403@gmail.com.
- Let the site sit live for a little while with real visits before applying.
- When you get your AdSense `ads.txt` snippet, add it to the repo root (it will replace/sit alongside the current `robots.txt`, which is a separate file), and paste your ad unit code into the `<div class="ad-slot">Ad space</div>` placeholders (search each `.html` file for `ad-slot`).

## About the file/image/video tools

- **Image Compressor, Image Resizer, Image Converter** — pure JavaScript using the browser's Canvas API. No external library.
- **Images to PDF, Merge PDF, PDF Compressor** — use [pdf-lib](https://pdf-lib.js.org/) (MIT license); PDF Compressor also uses [pdf.js](https://mozilla.github.io/pdf.js/) (Apache 2.0, made by Mozilla) to render pages. Both loaded from cdnjs.
- **Word to PDF** — uses [mammoth.js](https://github.com/mwilliamson/mammoth.js) to read the .docx and [html2pdf.js](https://github.com/eKoopmans/html2pdf.js) to render it to PDF, both from cdnjs.
- **Zip Files** — uses [JSZip](https://stuk.github.io/jszip/) (MIT license), from cdnjs.
- **Video Compressor** — uses [ffmpeg.wasm](https://github.com/ffmpegwasm/ffmpeg.wasm) (the open-source FFmpeg engine compiled to WebAssembly), loaded from unpkg. Downloads a ~25–30 MB engine the first time it's used per visit; works best on desktop browsers with a reasonably capable device, since it runs the whole video encode locally in the tab.
- **PDF Compressor** — works by re-rendering each PDF page as a compressed image and rebuilding the PDF from those images. This shrinks scanned or image-heavy PDFs very well, but text is no longer selectable/searchable afterwards — this trade-off is explained on the page itself.

All of these libraries are free, open-source and widely used — no fees, no accounts, no API keys. They only run in the visitor's browser; nothing is uploaded anywhere.

## Notes
- Colors, glow and every visual style live in `style.css` under `:root` — change `--signal` (red), `--paper` (background) and `--ink` (text) there to retint the whole site later.
- Tools needing a CDN library (Images to PDF, Merge PDF, PDF Compressor, Word to PDF, Zip Files, Video Compressor) and the QR generator need an internet connection. Every other tool works fully offline once the page has loaded.
