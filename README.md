# Higher Order Education — Enrolment Landing Page

Static landing page for in-home tutoring enrolment, served at
**join.higherordereducation.com.au**.

## Stack

A single static `index.html` — no build step, no dependencies. Fonts load from
Google Fonts and the enrolment form is embedded from LeadConnector (GoHighLevel).

It deploys as a Cloudflare **Workers** project using
[Static Assets](https://developers.cloudflare.com/workers/static-assets/):
`npx wrangler deploy` uploads everything in `public/` and serves it directly.

## Deploy on Cloudflare

The connected Workers build runs `npx wrangler deploy`, which reads
`wrangler.jsonc`. No build command or framework preset is needed — the static
files in `public/` are uploaded as-is.

### 1. Project settings (Cloudflare dashboard)

- **Deploy command:** `npx wrangler deploy` (default)
- **Build command:** *(leave empty)*
- Everything else is driven by `wrangler.jsonc`.

### 2. Add the custom domain

1. Open the Worker → **Settings → Domains & Routes → Add → Custom domain**.
2. Enter `join.higherordereducation.com.au`.
3. If `higherordereducation.com.au` is on Cloudflare DNS, the `CNAME` record is
   added automatically. Otherwise create a `CNAME` for `join` pointing at the
   Worker's route.
4. Cloudflare provisions the TLS certificate automatically.

### Local preview

```sh
npx wrangler dev
```

## Files

| File             | Purpose                                              |
|------------------|------------------------------------------------------|
| `wrangler.jsonc` | Cloudflare Workers config (points assets at `public/`). |
| `public/index.html` | The landing page.                                 |
| `public/_headers`   | Security headers applied to the served assets.    |
