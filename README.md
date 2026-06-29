# Muhammed Fawaz — Portfolio

A single, self-contained `index.html` (all CSS, JS, and the résumé PDF are inlined — no build step, no dependencies). Deploy it on any static host.

## Option A — GitHub Pages (free, recommended)

**Cleanest URL:** name the repo `FawazMV.github.io` → your site lives at `https://fawazmv.github.io/`.
(Any other repo name works too; the site is then at `https://fawazmv.github.io/<repo-name>/`.)

Using the GitHub CLI (`gh`):

```bash
cd ~/fawaz-portfolio
git init -b main
git add .
git commit -m "Portfolio"
gh repo create FawazMV.github.io --public --source=. --push
# then enable Pages (main / root):
gh api -X POST repos/FawazMV/FawazMV.github.io/pages -f source.branch=main -f source.path=/
```

Or via the website: create the repo, upload `index.html`, then **Settings → Pages → Build and deployment → Source: Deploy from a branch → main / (root) → Save**. Live in ~1 minute.

## Option B — Netlify Drop (free, fastest, no git)

Go to <https://app.netlify.com/drop> and drag the `fawaz-portfolio` folder onto the page. Instant URL. (Same idea works on Cloudflare Pages and Vercel.)

## Notes

- The **résumé download** works on real hosting (it may be blocked inside some sandboxed preview iframes, but not on GitHub Pages / Netlify).
- To use a **custom domain** later: add it under the host's domain settings and point your DNS — the host gives exact records, and HTTPS is automatic and free.
- To update the site after editing `index.html`: `git add . && git commit -m "update" && git push` (Pages redeploys automatically), or re-drag the folder on Netlify.
