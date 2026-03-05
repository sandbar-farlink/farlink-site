# Farlink Systems Website

Astro static site. Deploy on Cloudflare Pages via GitHub.

## Local Development

```bash
npm install
npm run dev
```

Site runs at `http://localhost:4321`

## Deploy to Cloudflare Pages

1. **Push to GitHub:**
   ```bash
   git init
   git add .
   git commit -m "Initial site"
   git remote add origin https://github.com/YOUR_USERNAME/farlink-site.git
   git branch -M main
   git push -u origin main
   ```

2. **Connect in Cloudflare:**
   - Go to Cloudflare Dashboard → Pages → Create a project
   - Connect your GitHub account and select the `farlink-site` repo
   - Build settings:
     - Framework preset: **Astro**
     - Build command: `npm run build`
     - Build output directory: `dist`
   - Click **Save and Deploy**

3. **Connect your domain:**
   - In Cloudflare Pages → your project → Custom domains
   - Add `farlinksystems.com` (and `www.farlinksystems.com` if desired)
   - Cloudflare will automatically configure the DNS records

## Project Structure

```
src/
├── components/
│   ├── Header.astro
│   └── Footer.astro
├── layouts/
│   └── Base.astro
├── pages/
│   ├── index.astro      (Home)
│   ├── about.astro       (About)
│   ├── services.astro    (Services)
│   └── contact.astro     (Contact)
└── styles/
    └── global.css
```

## Contact Form

The contact form is currently a static HTML form. For Cloudflare Pages, options include:
- **Cloudflare Workers** — write a simple worker to handle form submissions and send email
- **Formspree** or **Formspark** — third-party form backends (easiest)
- **Cloudflare Email Workers** — route form submissions to your inbox

## Notes

- Fonts loaded from Google Fonts (Barlow Condensed, DM Sans, JetBrains Mono)
- No JavaScript frameworks — pure Astro components with minimal client-side JS (mobile menu only)
- All pages are static — no server-side rendering needed
# farlink-site
