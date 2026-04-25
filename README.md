# Clovty.com

The website for **Clovty LLC**, a Wyoming-registered enterprise commerce intelligence firm.

This is a static, self-contained website. There is **no build step** — every page links to the
shared `styles.css` and runs as plain HTML/CSS/JS in any browser.

---

## File structure

```
clovty_site/
├── index.html        Home / landing
├── services.html     Solutions + engagement pricing
├── about.html        Company background, principles, legal facts
├── contact.html      Contact form + company details
├── privacy.html      Privacy Policy
├── terms.html        Terms of Service
├── 404.html          Error page (browser fallback)
├── styles.css        Shared stylesheet (no Tailwind, no build step)
├── robots.txt        Search-engine directive
├── sitemap.xml       Search-engine sitemap
├── favicon.svg       Browser tab icon
├── images/
│   ├── logo.svg      Wordmark icon (white-on-navy)
│   └── logo-light.svg Light variant (for dark backgrounds)
└── README.md         You are here
```

---

## Form handling

The contact form on `contact.html` is wired to a Formspree endpoint
(`https://formspree.io/f/xzdywbdp`). Submissions will be forwarded to the email address
configured in the Formspree dashboard. To change the destination email or endpoint, log in
at [formspree.io](https://formspree.io) and update the form, or replace the endpoint in
`contact.html` line 95.

---

## Deployment

This site is **fully static** and works on any free static-hosting platform.

### Option 1 — Cloudflare Pages (recommended, free, fastest CDN)

1. Push the `clovty_site/` directory to a GitHub repo.
2. Go to https://pages.cloudflare.com → **Create a project** → connect the repo.
3. Build command: *(leave blank)* · Build output directory: `/`
4. Click **Save and Deploy**.
5. Add your custom domain (`clovty.com`) under **Custom domains**.

### Option 2 — Netlify

1. Drag the `clovty_site/` folder onto https://app.netlify.com/drop — it deploys instantly.
2. Or connect the GitHub repo and select **Deploy site** with no build settings.
3. Add `clovty.com` under **Domain settings**.

### Option 3 — Vercel

1. Push to GitHub.
2. Import the repo at https://vercel.com → framework preset: **Other**.
3. Add the custom domain.

### Option 4 — GitHub Pages

1. Push to a public repo.
2. Settings → Pages → Source: `main` branch / root.
3. Custom domain: configure `clovty.com` and add the CNAME.

> **404 page:** Cloudflare Pages and Netlify automatically serve `404.html` for missing pages.
> Vercel and GitHub Pages serve it automatically as well. No additional configuration needed.

---

## Local preview

To preview the site on your laptop without any tooling:

```bash
cd clovty_site
python3 -m http.server 8080
# open http://localhost:8080 in your browser
```

Or just **double-click `index.html`** — it will open in your default browser.

---

## Editing content

All content is plain HTML. The pages share an identical `<header>`, `<footer>`, and overall
structure. To edit copy:

- **Hero / value-prop** → top of `index.html`
- **Solutions** → `services.html`
- **Company background, principles, legal facts** → `about.html`
- **Contact info, form fields** → `contact.html`
- **Privacy / Terms** → `privacy.html`, `terms.html`
- **Search-engine indexing** → `robots.txt`, `sitemap.xml`

To change the visual style globally, edit the CSS variables at the top of `styles.css`:

```css
:root {
  --bg: #ffffff;            /* page background (pure white) */
  --bg-soft: #f6f8fa;       /* alternate section background */
  --bg-dark: #0b1a30;       /* deep navy (footer, hero side, CTA) */
  --ink: #0a0e1a;           /* primary text */
  --accent: #134b9a;        /* corporate blue */
  ...
}
```

---

## Design notes

- **Aesthetic:** institutional / corporate B2B (think Stripe, Linear, McKinsey rather than
  boutique editorial). Pure white backgrounds, deep navy dark elements, single corporate blue
  accent, all sans-serif typography (Geist + Geist Mono via Google Fonts).
- **Restraint over flourish:** weight contrast carries hierarchy, not serif italics or color
  spans. Border radii are 4–6px (sharp/institutional), not 18–24px (soft/consumer).
- **Numbers and metrics** on the home page are presented as principles or framework items
  rather than as fabricated statistics — appropriate for a newly-formed entity.

---

## What is — and isn't — on this site

For Mercury (and any future bank/payments review), the site **deliberately includes**:

- Clear, specific business activity description (AI-powered e-commerce data analysis &
  enterprise business intelligence).
- The legal entity name and Wyoming registered address — matching the LLC formation documents.
- A Privacy Policy and Terms of Service, both written in plain English.
- Engagement pricing in USD with explicit payment-method statements (wire / ACH only,
  no crypto, no informal channels).
- A "what we don't do" section on the services page (compliance signal).
- A `compliance-band` strip on the home page summarizing entity, banking, and data posture.
- `robots.txt` and `sitemap.xml` so search-engine crawlers and bank-side automated reviewers
  index every page cleanly.

The site **deliberately omits**:

- The EIN (`42-2070921`) — referenced as "on file with the IRS" rather than printed publicly.
- The owner's name, residential address, or country of residence — those belong on the
  Mercury application, not on a public consulting site.
- Specific client logos / testimonials — leave those out until you actually have signed clients
  who have agreed to be named.
- Tracking, analytics, advertising pixels, and behavioral cookies — consistent with what the
  Privacy Policy claims.

---

## Tech notes

- **No frameworks.** Plain HTML, CSS, and a few lines of vanilla JavaScript for the mobile menu
  and scroll reveals.
- **Fonts** are loaded from Google Fonts (Geist + Geist Mono only — no serif). You can self-host
  them later if you prefer.
- **Accessibility:** semantic HTML, focusable controls, sufficient color contrast, descriptive
  `alt` attributes, `aria` labels on the navigation.
- **SEO:** every page has a unique `<title>` and `<meta name="description">`, Open Graph tags
  for social sharing, JSON-LD `Organization` schema on the homepage, plus the `robots.txt` and
  `sitemap.xml` files.

---

## License

All site content, copy, and design © 2026 Clovty LLC. All rights reserved.
