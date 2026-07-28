# Ridhanova — Go-Live Guide
**Domain:** ridhanova.com

## 1. What's in this package

```
index.html              ← the site (fully self-contained, no external CSS/JS files needed)
robots.txt               ← tells search engines what to crawl
sitemap.xml               ← page list for Google Search Console
site.webmanifest          ← homescreen/PWA icon config
CNAME                     ← tells GitHub Pages your custom domain
assets/icons/
  favicon.svg              ← scalable icon (modern browsers)
  favicon.ico               ← classic multi-size icon (16/32/48px)
  favicon-16x16.png
  favicon-32x32.png
  favicon-48x48.png
  apple-touch-icon.png       ← iOS homescreen icon (180px)
  android-chrome-192x192.png ← Android homescreen icon
  android-chrome-512x512.png ← Android splash / PWA icon
```

**Keep this folder structure exactly as-is** when you upload — `index.html` references icons at `/assets/icons/...`, so the `assets` folder must sit right next to `index.html` at the root of your repo.

---

## 2. Push to GitHub Pages

1. In your GitHub repo, upload all files from this package to the **root** (not a subfolder) of the `main` branch — replace the existing `index.html` and add the new files alongside it.
2. Go to **Settings → Pages** → Source: `main` branch → `/root` → Save.
3. Wait 1–2 minutes for the deploy to finish (check the green checkmark under the **Actions** tab).

---

## 3. Point ridhanova.com to GitHub Pages

In your domain registrar's DNS settings (GoDaddy, etc.):

**A records** — add all four, pointing `@` (root domain) to GitHub Pages' IPs:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

**CNAME record** — point `www` to your GitHub Pages URL:
```
www   CNAME   <your-github-username>.github.io
```

Back in GitHub: **Settings → Pages → Custom domain** → enter `ridhanova.com` → Save. GitHub will verify the `CNAME` file (already included in this package) and issue an SSL certificate automatically — this can take up to 24 hours. Once ready, tick **Enforce HTTPS**.

---

## 4. After it's live — submit to search engines

1. **Google Search Council** ([search.google.com/search-console](https://search.google.com/search-console)):
   - Add property → `ridhanova.com`
   - Verify ownership (GitHub Pages supports the HTML file or DNS TXT method)
   - Submit sitemap: `https://ridhanova.com/sitemap.xml`

2. **Bing Webmaster Tools** ([bing.com/webmasters](https://www.bing.com/webmasters)) — same steps, smaller but still worth doing.

3. **Google Business Profile** — create/claim a listing for Ridhanova Workforce Solutions at your Madipakkam address. This matters more than almost anything else for local "recruitment agency near me" searches in Chennai.

---

## 5. What's already built into the site

- **Meta tags** — title, description, and keywords tuned for "recruitment agency Chennai" / "HR consulting Tamil Nadu" type searches
- **Open Graph + Twitter Card tags** — so WhatsApp/LinkedIn/Facebook/Twitter shares show a proper title, description, and preview image instead of a blank link
- **Structured data (JSON-LD)** — tells Google this is an `EmploymentAgency`, with your address, phone, hours, and coordinates, which helps you show up in Google Maps / local pack results
- **Canonical URL + robots meta** — prevents duplicate-content issues
- **Geo tags** — reinforces the Chennai/Tamil Nadu local-search signal

## 6. Things worth doing next (not included here)

- **Privacy Policy / Terms & Conditions** — the footer links to these but no content exists yet; I held off writing legal text without your review. Let me know if you want a basic draft.
- **Google Analytics / Meta Pixel** — not installed. Say the word and I'll wire in GA4 or a Meta Pixel once you have the tracking ID.
- **Backlinks** — get listed on Chennai business directories (Justdial, Sulekha, IndiaMART) linking back to ridhanova.com; this helps domain authority more than any on-page tweak.
