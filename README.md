# ToolKrate — Free Utility Tools Website

Static site, 23 real client-side tools + About/Contact/Privacy pages. No backend server — pure HTML/CSS/JS (a few tools load a small, well-known JS library from a CDN for PDF/video/zip work, listed below). Black-and-red theme with glowing buttons and cards. All processing happens in the visitor's browser.

## Tools included

**Text & writing:** Word/Character Counter, Case Converter, JSON Formatter, Base64 Encode/Decode
**Calculators:** BMI, Age, Percentage, Loan/EMI, Zakat, Unit Converter
**Generators & utilities:** Password Generator, QR Code Generator, Color Converter
**File & image tools:** Image Compressor, Image Resizer, Image Converter (PNG/JPG/WebP), Images to PDF, Merge PDF, Word (.docx) to PDF, Zip Files, Video Compressor, PDF Compressor, **File Compressor** (auto-detects any file type and applies the matching method)

## Deploy to GitHub + Vercel

1. Create a new (empty) repository on GitHub, or open your existing `toolkrate` repo.
2. Upload/replace every file in this folder, keeping the `tools/` folder structure intact.
3. If already connected to Vercel, it redeploys automatically within a minute or two of the GitHub push.
4. `sitemap.xml` and `robots.txt` are already pointed at `https://toolkrate.vercel.app`, and the Google-site-verification tag is already in `index.html`.

## What changed in this update

- **Downloaded filenames now reflect the original file** instead of a generic name like "compressed.pdf":
  - PDF Compressor & File Compressor (PDF path): exact same filename, since the file stays a PDF.
  - Image Compressor: original name + `.jpg` (output is always JPEG).
  - Image Resizer: original name + `.png` (output is always PNG).
  - Image Converter: original name + whichever extension you picked to convert to.
  - Video Compressor & File Compressor (video path): original name + `.mp4` (output is always an MP4 container).
  - Zip Files (single file): original name + `.zip`.
- **New: File Compressor** (`/tools/file-compressor.html`) — one file picker that detects what you dropped in and compresses it the right way: images via quality re-encoding, PDFs via page rasterization, videos via a real browser video encoder, and anything else (docs, spreadsheets, code, etc.) via a lossless .zip bundle. The dedicated Image/PDF/Video/Zip tools still exist separately for anyone who wants more manual control.

## Before you apply for AdSense

- Contact page is already set to zaidsarwar1403@gmail.com.
- Let the site sit live for a little while with real visits before applying.
- When you get your AdSense `ads.txt` snippet, add it to the repo root, and paste your ad unit code into the `<div class="ad-slot">Ad space</div>` placeholders (search each `.html` file for `ad-slot`).

## About the file/image/video tools

- **Image Compressor, Image Resizer, Image Converter** — pure JavaScript using the browser's Canvas API. No external library.
- **Images to PDF, Merge PDF, PDF Compressor** — use [pdf-lib](https://pdf-lib.js.org/) (MIT license); PDF Compressor also uses [pdf.js](https://mozilla.github.io/pdf.js/) (Apache 2.0, Mozilla) to render pages. Loaded from cdnjs.
- **Word to PDF** — uses [mammoth.js](https://github.com/mwilliamson/mammoth.js) and [html2pdf.js](https://github.com/eKoopmans/html2pdf.js), both from cdnjs.
- **Zip Files** — uses [JSZip](https://stuk.github.io/jszip/) (MIT license), from cdnjs.
- **Video Compressor** — uses [ffmpeg.wasm](https://github.com/ffmpegwasm/ffmpeg.wasm) (open-source FFmpeg compiled to WebAssembly), from unpkg. Downloads a ~25–30 MB engine the first time it's used per visit.
- **File Compressor** — combines all of the above, loading each library only when a matching file type is dropped in (so visitors who only compress images never download the PDF/video engines).

All libraries are free, open-source and widely used — no fees, no accounts, no API keys. Everything runs in the visitor's browser; nothing is uploaded anywhere.

## Notes
- Colors, glow and every visual style live in `style.css` under `:root`.
- Tools needing a CDN library and the QR generator need an internet connection. Every other tool works fully offline once the page has loaded.
