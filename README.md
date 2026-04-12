# Tribute Page

A single-file website for collecting stories, memories, and messages for someone you love. Built for retirements, milestone birthdays, memorials, or any occasion worth celebrating.

No frameworks. No build step. No backend to manage. Just one HTML file, a free hosting provider, and a form service.

## What You Get

- Full-screen hero section with a photo of your loved one
- Rich text editor (bold, italics, headings, colors, fonts) so people can write like they would in a word doc
- Photo upload with drag-and-drop, previews, and remove buttons
- Mobile responsive out of the box
- Submissions delivered to your email via [Formspree](https://formspree.io)

## Demo

Here's what it looks like in action -- this was originally built for a retirement celebration:

**[Live Example: Tom Kenslea — Going Fishing](examples/tom-kenslea.html)**

## Quick Start

The whole setup takes about 10 minutes.

### 1. Fork or download this repo

Click the green **Code** button above and download the ZIP, or fork it to your own GitHub account.

### 2. Set up Formspree (5 minutes)

[Formspree](https://formspree.io) handles form submissions so you don't need a server.

1. Create a free account at [formspree.io](https://formspree.io)
2. Click **New Form** and give it a name (e.g., "Dad's Retirement")
3. Copy your form endpoint — it looks like `https://formspree.io/f/xAbCdEfG`
4. Open `index.html` and find this line near the bottom:
   ```js
   var FORM_ENDPOINT = 'YOUR_FORMSPREE_ENDPOINT_HERE';
   ```
5. Replace `YOUR_FORMSPREE_ENDPOINT_HERE` with your actual endpoint

> **Important:** Create your own Formspree account and endpoint. Do not reuse someone else's — submissions go directly to whatever email is tied to that endpoint.

### 3. Customize the content

Open `index.html` and update these sections:

| What to change | Where to find it |
|---|---|
| Page title | `<title>` tag in `<head>` |
| Hero photo | `<img>` tag `src` in the hero section — use any image URL |
| Hero title | `<h1 class="tk-hero-title">` |
| Hero subtitle | `<p class="tk-hero-subtitle">` |
| Hero detail text | `<p class="tk-hero-detail">` |
| Form heading | `<h2>Add Yours</h2>` |
| Form description | The `<p>` tags inside `.tribute-header` |
| Story prompt | `<label class="section-label">` above the editor |
| Editor placeholder | `placeholder: 'I remember when…'` in the JavaScript |
| Success message | Inside `.tribute-success` near the bottom |

### 4. Deploy for free

Pick any of these — they're all free for a single static page:

**GitHub Pages** (recommended if you forked the repo):
1. Go to your repo's **Settings → Pages**
2. Set source to **Deploy from a branch**, select `main`, root `/`
3. Your site will be live at `https://yourusername.github.io/repo-name`

**Netlify** (easiest for non-developers):
1. Go to [netlify.com](https://www.netlify.com) and sign up
2. Drag and drop your `index.html` file into the dashboard
3. Done — you'll get a URL like `https://something.netlify.app`

**Cloudflare Pages:**
1. Connect your GitHub repo at [pages.cloudflare.com](https://pages.cloudflare.com)
2. It auto-deploys on every push

**Custom domain** (optional): All of the above support custom domains for free. You'd buy a domain (~$10-15/year from Namecheap, Google Domains, etc.) and point the DNS records to your host.

## Cost

| Item | Cost |
|---|---|
| Hosting (GitHub Pages / Netlify / Cloudflare) | **Free** |
| Custom domain (optional) | ~$10-15/year |
| Formspree — Free tier | **$0/month** — 50 submissions/month, text only (no photo uploads) |
| Formspree — Starter tier | **$15/month** — 200 submissions/month, photo uploads included |

**Total: $0 to $15/month** depending on whether you want photo uploads.

### Do I need the paid Formspree tier?

- **Text-only messages** (no photos): The free tier works. You get 50 submissions per month at no cost.
- **Messages + photo uploads**: You need the Starter plan ($15/month). Formspree's free tier doesn't support file attachments.

### Can I cancel after the event?

Yes. Formspree is month-to-month, no commitment. Subscribe for one month while you're collecting responses, download your submissions, and cancel. The website itself stays up for free — only the form stops accepting new submissions.

## Customization Tips

**Change the color scheme:** The accent color is `#1a1a1a` (black). Search and replace it with any hex color to match your vibe.

**Change fonts:** The page uses [Lora](https://fonts.google.com/specimen/Lora) (serif, for headings and the editor) and [Inter](https://fonts.google.com/specimen/Inter) (sans-serif, for UI). Swap them in the Google Fonts `<link>` tag and the CSS `font-family` rules.

**Add more form fields:** Add a new `<div class="tribute-field">` block with a label and input. The field's `name` attribute is what shows up in your Formspree submissions.

**Remove photo uploads:** Delete the upload zone HTML block (from `Photographic Proof` label through the closing `</div>` of `.upload-zone`) and remove the `setupUploadZone` call in the JavaScript.

**Use on Squarespace or other site builders:** The HTML works inside a Squarespace Code Block too. Just paste the contents of `index.html` (everything inside `<body>`) into a Code Block with "Display Source" unchecked. Note: the full-bleed hero may be constrained by the site builder's container.

## Tech Stack

- **[Quill.js](https://quilljs.com)** — Rich text editor (loaded via CDN)
- **[Formspree](https://formspree.io)** — Form submission handling (no server needed)
- **[Google Fonts](https://fonts.google.com)** — Lora + Inter
- Vanilla HTML, CSS, JavaScript — no build tools, no frameworks, no dependencies to install

## License

MIT — do whatever you want with it. See [LICENSE](LICENSE).
