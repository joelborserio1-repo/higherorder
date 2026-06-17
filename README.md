# Higher Order Education — Enrolment Landing Page

Static landing page for in-home tutoring enrolment, served at
**join.higherordereducation.com.au**.

## Stack

A single static `index.html` — no build step, no dependencies. Fonts load from
Google Fonts and the enrolment form is embedded from LeadConnector (GoHighLevel).

## Deploy on Cloudflare Pages

This repo is set up for a no-build static deploy.

### 1. Create the project

1. In the Cloudflare dashboard go to **Workers & Pages → Create → Pages → Connect to Git**.
2. Select this repository and the production branch.
3. Build settings:
   - **Framework preset:** None
   - **Build command:** *(leave empty)*
   - **Build output directory:** `/`
4. Click **Save and Deploy**.

### 2. Add the custom domain

1. Open the Pages project → **Custom domains → Set up a custom domain**.
2. Enter `join.higherordereducation.com.au`.
3. If `higherordereducation.com.au` is on Cloudflare DNS, the `CNAME` record is
   added automatically. Otherwise create a `CNAME` for `join` pointing at the
   project's `*.pages.dev` hostname.
4. Cloudflare provisions the TLS certificate automatically.

## Files

| File         | Purpose                                              |
|--------------|------------------------------------------------------|
| `index.html` | The landing page.                                    |
| `_headers`   | Security headers applied by Cloudflare Pages.        |
