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
| `robots.txt` | Keeps the preview copy out of search results — see below |

## Putting it online

Copy every file in this folder into the web root of the hosting account
(`public_html` on cPanel). Nothing needs to be installed or compiled.

Two things to do once the files are there:

1. **Issue an SSL certificate** and turn on the redirect from `http://` to
   `https://`. The certificate on investsure.ca expired in August 2023.
2. **Delete `robots.txt`**, or replace its contents with `User-agent: *` and
   `Allow: /`. On the real domain the site has to be indexed; the file in this
   repository exists only to keep the preview copy invisible to Google.

Do not change the MX records: the mail for `info@investsure.ca` runs through
Microsoft 365 and is not touched by the website.

## Editing a broker

Open `index.html` and find `var BROKERS = [`. Each broker is one block:
name, role, photo file, email, phone, Instagram handle, website, languages,
a short biography and three bullet points. An empty value means the row simply
does not appear on the page.
