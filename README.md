# Mema Website

This directory contains the static website for Mema, hosted on GitHub Pages at [memaphotos.com](https://memaphotos.com).

## Pages

- **index.html** - Landing page with product overview and value proposition
- **privacy.html** - Privacy policy (required for App Store/Play Store submission)
- **support.html** - Support page with FAQ and contact information

## Waitlist (Optional)

By default, the landing page uses a simple **mailto** link for “Join the waitlist”, which keeps the site static and
avoids third-party tracking/scripts.

If you later want an in-page signup form (email capture) on a static host like GitHub Pages:

1. Add your provider’s embed code / form action to `web/index.html`.
2. Update `web/privacy.html` to reflect the provider and data handling.

## Local Preview

To preview the site locally, simply open the HTML files in your browser:

```bash
# macOS
open web/index.html

# Linux
xdg-open web/index.html

# Or use a simple HTTP server
cd web
python3 -m http.server 8000
# Then visit http://localhost:8000
```

## Deployment

### Initial Setup

1. Create a new repository at `git@github.com:Artomatica/memaphotos.com.git`
2. Copy the `web/` directory contents to the repository root
3. Push to GitHub
4. Enable GitHub Pages in repository settings (Settings → Pages → Source: main branch)

### Custom Domain Setup

The site is configured for the custom domain `memaphotos.com`.

**DNS Configuration (Namecheap):**

Add the following DNS records in Namecheap:

```
Type    Host    Value                       TTL
A       @       185.199.108.153             Automatic
A       @       185.199.109.153             Automatic
A       @       185.199.110.153             Automatic
A       @       185.199.111.153             Automatic
CNAME   www     artomatica.github.io        Automatic
```

**GitHub Pages Configuration:**

1. Go to repository Settings → Pages
2. Under "Custom domain", enter: `memaphotos.com`
3. Check "Enforce HTTPS" (after DNS propagates)

### Updates

To update the website:

```bash
cd /path/to/memaphotos.com
# Edit HTML files
git add .
git commit -m "Update website content"
git push origin main
```

Changes will be live within a few minutes.

## Design Notes

- **Static hosting friendly**: Works on GitHub Pages
- **Mobile-responsive**: Works on all screen sizes
- **Fast loading**: No JS frameworks; no tracking scripts
- **Accessible**: Semantic HTML, proper heading hierarchy
- **SEO-friendly**: Meta descriptions, proper titles, clean URLs

## Store Submission URLs

Use these URLs for App Store and Play Store submissions:

- **Privacy Policy**: https://memaphotos.com/privacy.html
- **Support URL**: https://memaphotos.com/support.html
- **Marketing URL**: https://memaphotos.com

## Contact

- Email: support@memaphotos.com
- Privacy: privacy@memaphotos.com
