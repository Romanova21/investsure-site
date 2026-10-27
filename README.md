# Investsure Financial Inc. — website

A static site: plain HTML, CSS and JavaScript written into the page itself.
There is no server code, no database and no build step. Whatever is in this
folder is the whole site.

## Files

| File | What it is |
|---|---|
| `index.html` | The site — every section, and the broker data near the bottom of the file |
| `privacy.html` | Privacy policy (PIPEDA) |
| `*.jpg`, `*.png` | Photographs and the logo |

## Preview

Until the domain is switched, the site is visible at
https://romanova21.github.io/investsure-site/ — every push to `main` shows there
within a minute or two. Both pages name `https://www.investsure.ca/` as their
canonical address, so search engines credit the real domain, not the preview.

## Putting it online

The domain `investsure.ca` is registered at GoDaddy (DNS servers
`ns07/ns08.domaincontrol.com`). There are two ways to publish; choose one.

### Option A — point the domain at this repository (recommended, done once)

In GoDaddy → My Products → investsure.ca → DNS, change only these records:

| Type | Name | Value | Action |
|---|---|---|---|
| A | `@` | `50.63.179.127` | delete (the old hosting) |
| A | `@` | `185.199.108.153` | add |
| A | `@` | `185.199.109.153` | add |
| A | `@` | `185.199.110.153` | add |
| A | `@` | `185.199.111.153` | add |
| CNAME | `www` | `romanova21.github.io` | change (now it points to `@`) |

Then, in this repository: Settings → Pages → Custom domain `www.investsure.ca`,
and tick "Enforce HTTPS" once GitHub has issued the certificate (it does that
itself, usually within an hour). From then on every change is a push to `main`;
nobody needs the GoDaddy account again.

### Option B — upload the files to the GoDaddy hosting

Copy every file except `README.md` and `.gitignore` into the web root of the
hosting account (`public_html` on cPanel). Then issue an SSL certificate and turn
on the redirect from `http://` to `https://` — the certificate on investsure.ca
expired in August 2023. Every later change has to be uploaded the same way.

### Either way

Do not touch the MX and TXT records: the mail for `info@investsure.ca` runs
through Microsoft 365 and is not part of the website.

## Editing a broker

Open `index.html` and find `var BROKERS = [`. Each broker is one block:
name, role, photo file, email, phone, Instagram handle, website, languages,
a short biography and three bullet points. An empty value means the row simply
does not appear on the page.
