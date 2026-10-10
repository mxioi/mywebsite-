# Isle of Wight Takeover 2027

A static countdown website for the Isle of Wight Takeover 2027, live at https://iowto.mxioi.uk.

## Overview

The site is a single page (`index.html`) with:
- A full-screen hero with a live countdown to Show Day
- The weekend schedule (Takeover Party Saturday 15 May, Show Day Sunday 16 May 2027)
- Venue, tickets, travel and what-to-bring info
- A photo gallery with a tap-to-enlarge viewer
- A map of the venue and links to the WhatsApp group
- Light and dark mode (follows the visitor's system setting, with a toggle)

It uses plain HTML, CSS and JavaScript with no build step. Leaflet draws the map.

## Updating event details

Everything you are likely to change lives in the **SITE CONFIG** block near the bottom of `index.html`:

```js
const EVENT_START = '2027-05-16T10:00:00+01:00'; // countdown target (BST = +01:00)
const PHOTOS = [ ... ];                          // gallery photos, in order
const VENUE = { lat, lng, name, address };       // map pin
```

The text on the page (dates, venue card, location section) is plain HTML; search `index.html` for
"2027" or "TBC" to find it. When the 2027 venue is announced, update:
1. The **Venue** card in the "Everything you need" section
2. The **Location** section card (name, address, Google Maps link)
3. `VENUE` in the SITE CONFIG block

## Photos

- `images/iow-2027/`: put 2027 photos here. See `images/iow-2027/README.md` for sizing and how to add them to the gallery.
- `images/iow-2025/`: photos from previous Takeovers, web-sized (shown until 2027 photos are added).

## Local Development

### Quick Preview

Run the preview script to test locally:

```bash
./scripts/preview.sh
```

This starts a simple HTTP server on port 8000. Open http://localhost:8000 in your browser.

### Alternative Preview Methods

If you have Node.js:
```bash
npx serve
```

If you have Python 3:
```bash
python3 -m http.server 8000
```

## Deployment

This site is configured for GitHub Pages:

1. Ensure the `CNAME` file contains your custom domain (if using one)
2. Push changes to the `main` branch
3. GitHub Pages will automatically deploy the site
4. HTTPS is enforced (recommended for security)

## Technologies Used

- **HTML5** with semantic markup
- **Hand-written CSS** with light/dark theme variables
- **Leaflet** + OpenStreetMap for the venue map
- **Vanilla JavaScript** for the countdown, gallery and lightbox
- **Cloudflare Turnstile** for bot protection

## File Structure

```
.
├── index.html              # Main countdown page
├── privy.html             # Privacy policy page
├── manifest.json          # PWA manifest
├── robots.txt             # Search engine directives
├── sitemap.xml            # Site map for SEO
├── CNAME                  # Custom domain configuration
├── images/
│   ├── iow-2025/         # Previous event photos (web-sized)
│   └── iow-2027/         # 2027 event photos (add yours here)
└── scripts/
    └── preview.sh        # Local preview server script
```

## Accessibility

The site includes:
- ARIA labels for countdown timer
- Semantic HTML structure
- Alt text for all images
- Keyboard navigation support
- Responsive design for all screen sizes
- High contrast color scheme

## Security

- Content Security Policy (CSP) headers
- HTTPS enforcement (via GitHub Pages)
- Bot protection via Cloudflare Turnstile
- No external form submissions

## Browser Support

Tested and working on:
- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## Contributing

1. Create a feature branch: `git checkout -b feat/your-feature`
2. Make your changes
3. Test locally using preview script
4. Commit with descriptive messages
5. Push and create a pull request

## License

© Isle of Wight Takeover community. All rights reserved.
