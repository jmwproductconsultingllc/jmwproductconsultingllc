# Deploying jmwproductconsulting.com to Vercel

This folder is a complete, static site. `index.html` is the whole site; everything
it needs is here. Pick ONE of the two paths below.

---

## ✅ Before you deploy (2-minute checklist)

1. **Booking link** — DONE: all CTAs point to the Google Calendar appointment schedule (`BOOKING_URL` in the script).
2. **Headshot** — drop your photo into this folder named exactly **`jason-headshot.png`**.
   (If you skip it, the site shows a clean "JW" placeholder — it won't break.)
3. That's it. The favicon and OG share image are already wired up.

---

## Option A — Vercel CLI (fastest, no GitHub needed)

Requires Node.js installed. In your terminal:

```bash
npm i -g vercel          # install the CLI (one time)
cd path/to/jmw-site      # this folder
vercel login             # sign in (email / GitHub)
vercel                   # creates a preview deployment, asks a few questions
vercel --prod            # promotes it to production
```

When prompted:
- "Set up and deploy?" → **Y**
- "Which scope?" → your account
- "Link to existing project?" → **N** (first time)
- "Project name?" → `jmw-product-consulting` (or anything)
- "In which directory is your code?" → **`./`**
- Framework preset → **Other** ; Build command → leave empty ; Output dir → **`./`**

## Option B — GitHub + Vercel dashboard (best for ongoing edits)

1. Create a new GitHub repo and push this folder's contents (with `index.html` at the root).
2. In Vercel → **Add New… → Project** → **Import** that repo.
3. Framework Preset: **Other**. Leave Build Command empty. Output Directory: **`./`**.
4. Click **Deploy**. Every future `git push` auto-deploys.

---

## Connecting your domain (jmwproductconsulting.com)

1. In the Vercel project → **Settings → Domains** → add `jmwproductconsulting.com`
   and `www.jmwproductconsulting.com`.
2. Vercel shows the DNS records to set. At your domain registrar, either:
   - point the apex `A` record / `CNAME` as Vercel instructs, or
   - change nameservers to Vercel's (simplest if the domain isn't used elsewhere).
3. SSL is issued automatically once DNS propagates (usually minutes).

---

## Files in this bundle
- `index.html` — the site (self-contained)
- `og-image.png` — social share preview (referenced by the meta tags)
- `vercel.json` — production headers + caching (optional but recommended)
- `assets/` — your brand icons (SVG + PNG) for reuse; not required by the page
- `jason-headshot.png` — **you add this**
