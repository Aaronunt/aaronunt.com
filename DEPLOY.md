# Deploying aaronunt.com

The site is 3 static files (`index.html`, `robots.txt`, `sitemap.xml`). No build step. Any static host works.

## Before deploying

1. Add the headshot: save the same photo used on LinkedIn/X as `aaron-unt.jpg` in this folder, then uncomment the `<img class="hero-photo">` line in `index.html`. Using the same photo everywhere matters: it is the image Google will most likely pull into the card.

## Fastest deploy options (pick one)

### Cloudflare Pages (free, recommended)
1. Go to https://pages.cloudflare.com, sign in.
2. Create a project → Direct upload → drag this `site/` folder in.
3. In the project settings, add custom domain `aaronunt.com` (and `www.aaronunt.com`).
4. Update the domain's DNS to the records Cloudflare shows (at your registrar).

### Netlify (free)
1. Go to https://app.netlify.com/drop and drag this `site/` folder in.
2. Site settings → Domain management → add `aaronunt.com`, follow the DNS instructions.

### Vercel (free)
1. `npm i -g vercel` then run `vercel` inside this folder, or drag-drop at https://vercel.com/new.
2. Add `aaronunt.com` as a custom domain in the dashboard.

Whichever host: make sure `https://aaronunt.com/` loads with HTTPS (all three do this automatically).

## Immediately after the site is live (critical for the card)

1. **Google Search Console**: https://search.google.com/search-console
   - Add property `aaronunt.com` (Domain property; verify via the DNS TXT record the wizard gives you).
   - Sitemaps → submit `https://aaronunt.com/sitemap.xml`.
   - URL inspection → enter `https://aaronunt.com/` → **Request indexing**.
2. **Validate the schema**: paste `https://aaronunt.com/` into https://validator.schema.org and https://search.google.com/test/rich-results. Both should detect a `Person`.
3. **Close the loop on Wikidata**: on https://www.wikidata.org/wiki/Q140445361 add statement `official website (P856)` → `https://aaronunt.com`. Now the website points at Wikidata (sameAs) and Wikidata points at the website. That two-way link is the strongest entity signal you can create yourself.
4. **Link the site from your profiles**: add `aaronunt.com` as the website field on LinkedIn, X, and GitHub. This confirms ownership signals in both directions.

## Then

Wait and check Google every week or so. Typical time for a panel after Wikidata + indexed entity home: 2 to 6 weeks. If nothing after that, the next lever is an Estonian Wikipedia article.
