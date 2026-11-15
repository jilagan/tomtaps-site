# tomtaps.com

Static one-page marketing site for **Tom Taps – AAC Board** (App Store ID `6760241580`), hosted on GitHub Pages. Replaces the old WordPress 5.1 site.

## Files
- `index.html` — the site (self-contained; inline CSS, light/dark aware, responsive)
- `privacy.html` — privacy policy (also used as the App Store Privacy Policy URL)
- `assets/icon.png` — app icon (from `AppIcon_1024.png`)
- `.nojekyll` — serve files as-is (no Jekyll processing)

## Deploy
Pushed to `main`; GitHub Pages serves from the `main` branch, root. Preview URL:
`https://jilagan.github.io/tomtaps-site/`

To update: edit, commit, push to `main`. Pages redeploys in ~1 min.

## Custom-domain cutover (tomtaps.com → this site)
The domain's DNS is on **AWS Route 53** (in the site owner's AWS account); the old site is a WordPress box on **EC2 (us-west-2)**. To point tomtaps.com here:

1. Add a `CNAME` file to this repo containing `tomtaps.com`, and set the custom domain under repo **Settings → Pages**.
2. In **Route 53**, replace the apex `tomtaps.com` A records (currently the EC2 IPs) with GitHub Pages' apex IPs:
   - `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - and a `CNAME` for `www` → `jilagan.github.io`
3. Wait for DNS to propagate, then enable **Enforce HTTPS** in Settings → Pages.
4. Once live and verified, **decommission the old EC2 WordPress instance** (7-year-old WordPress 5.1 = security liability).

Until step 1–2 are done, the site is live only at the `github.io` URL above; tomtaps.com still shows the old WordPress site.

## Notes
- Support email `support@tomtaps.com` is referenced in the footer, the privacy page and the YouTube channel. It is live and delivers to joben@archmob.com (tested Oct 24, 2026).
- YouTube channel: https://www.youtube.com/@TomTapsAAC (Brand Account under joben.ilagan@gmail.com). `@TomTaps` belongs to an unrelated gaming channel.
- Symbols credit: Mulberry Symbol Set (CC BY-SA 4.0), already attributed in the footer and in-app.
