# Higher Order Education — Enrolment Landing Page

Static landing page for in-home tutoring enrolment, served at
**join.higherordereducation.com.au** via Cloudflare Pages.

## Stack

A single static `index.html` — no build step, no dependencies. Fonts load from
Google Fonts and the enrolment form is embedded from LeadConnector (GoHighLevel).

## Deploy on Cloudflare Pages

No build is required — the static files live at the repo root.

### Project settings (Cloudflare dashboard)

- **Framework preset:** None
- **Build command:** *(leave empty)*
- **Build output directory:** `/` (repo root)

A push to the production branch triggers a new deployment automatically.

### Manual deploy (optional)

From a machine with Node and a Cloudflare API token:

```sh
npx wrangler pages deploy . --project-name=<your-pages-project>
```

### Custom domain

In the Pages project → **Custom domains → Set up a custom domain** →
`join.higherordereducation.com.au`. TLS is provisioned automatically.

## Files

| File         | Purpose                                              |
|--------------|------------------------------------------------------|
| `index.html` | The landing page.                                    |
| `_headers`   | Security + cache headers applied by Cloudflare Pages.|
