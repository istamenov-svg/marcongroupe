# marcongrp.com

Static website for Marcon Groupe LLC. Hosted on GitHub Pages, custom domain `marcongrp.com`.

## Stack

- Plain HTML, CSS, JavaScript
- No build step
- No frameworks
- Google Fonts (Source Serif 4, Inter Tight)
- Formspree for contact form submissions
- Cloudflare Email Routing (or equivalent) for email forwarding

## Repository structure

```
.
├── index.html                                    Homepage
├── 404.html                                      Custom 404
├── thank-you.html                                Form submission confirmation
├── contact.html                                  Contact form
├── services/
│   ├── commercial-diligence.html
│   ├── vendor-cost-engineering.html
│   ├── fractional-cmo-operating-partner.html
│   └── front-office/
│       ├── index.html                            Front Office hub
│       ├── transformation.html
│       ├── diagnostic.html
│       ├── commercial-model-redesign.html
│       ├── team-and-accountability.html
│       ├── martech-and-data-rebuild.html
│       ├── demand-and-conversion.html
│       ├── customer-path-architecture.html
│       └── agentic-operations.html
├── assets/
│   ├── css/styles.css                            Single stylesheet for entire site
│   ├── js/site.js                                Persona tabs + mobile nav
│   └── img/                                      (Empty — logo and imagery to be added)
├── CNAME                                         GitHub Pages custom domain
├── robots.txt
├── sitemap.xml
├── _build_services.py                            Generator for service pages (DEV ONLY — do not deploy)
└── README.md
```

## GitHub Pages setup

1. Create a public repository on GitHub
2. Push this entire directory to the `main` branch
3. Repository Settings → Pages
   - Source: **Deploy from a branch**
   - Branch: **main** / Folder: **/ (root)**
4. Custom domain: enter `marcongrp.com`, save
5. Enable **Enforce HTTPS** (may require waiting a few minutes for the certificate to provision)

## DNS configuration

Configure these records at your domain registrar for `marcongrp.com`:

**Apex domain (marcongrp.com) → A records pointing to GitHub Pages:**

```
A    @    185.199.108.153
A    @    185.199.109.153
A    @    185.199.110.153
A    @    185.199.111.153
```

**www subdomain → CNAME:**

```
CNAME    www    <your-github-username>.github.io
```

GitHub's IP addresses can change. Verify current values at:
https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site

## Formspree setup

1. Log in to Formspree, create a new form titled "Marcon Groupe — Contact"
2. Set the email destination to `info@marcongrp.com`
3. Copy the form's endpoint URL (looks like `https://formspree.io/f/xxxxxxxx`)
4. Open `contact.html`, find the line:
   ```html
   <form class="contact-form" action="https://formspree.io/f/REPLACE_WITH_FORMSPREE_ID" method="POST">
   ```
5. Replace `REPLACE_WITH_FORMSPREE_ID` with your actual Formspree form ID
6. Test by submitting the form; you should receive an email at `info@marcongrp.com` and the user should land on `/thank-you.html`

## Email forwarding setup

Use Cloudflare Email Routing (free) or Improvmx (free tier).

Cloudflare Email Routing:
1. Add `marcongrp.com` to Cloudflare (point nameservers to Cloudflare if not already)
2. Email Routing → Routes → add: `info@marcongrp.com` → forward to your personal inbox
3. Cloudflare auto-configures the required MX and TXT records

Test by sending a message to `info@marcongrp.com` from an external address.

## Local development

The site is plain HTML/CSS/JS. Open `index.html` in a browser, or run a local server:

```bash
python3 -m http.server 8000
# Then visit http://localhost:8000
```

## Editing service pages

Service pages are generated from `_build_services.py` for consistency. To edit a service page:

1. Open `_build_services.py`
2. Find the page entry in the `PAGES` list
3. Edit the relevant section (hero, sections, cta, meta)
4. Run: `python3 _build_services.py`
5. Commit the regenerated HTML files

The Front Office hub (`services/front-office/index.html`), homepage (`index.html`), contact (`contact.html`), 404, and thank-you pages are hand-edited HTML — they do not go through the build script.

`_build_services.py` is a development tool. It does not need to be deployed but leaving it in the repo is harmless.

## What's in v1, what's deferred

**v1 (this site):**
- Full service roster across Diligence, Build, Operate
- Persona tabs on homepage (PE Sponsors, Operators, Founders)
- Logo band ("Where we've operated")
- Contact form via Formspree
- Static, no tracking, no analytics

**Deferred to v2:**
- Chatbot with handoff to direct conversation
- Insights / blog
- Case studies or named client work
- Principal bio / About page
- Newsletter
- Analytics (Plausible, Fathom, or Google Analytics)
- Buyer-segmented service page variants

## License

© 2026 Marcon Groupe LLC. All rights reserved. Site content and code are proprietary.
