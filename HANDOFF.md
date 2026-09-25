# RichieRich Transportation LLC — Website Handoff Guide

This is a single-page website. Everything lives in one file (`index.html`) plus
an `images/` folder. There's no database, no monthly bill, and nothing to log
into day-to-day. This guide covers the few things you need to know.

---

## ✅ 1. Forms (quotes and job applications)

Both forms are sent through **FormSubmit** (free, unlimited submissions) to
**richard18olvera@gmail.com**. Subject lines tell them apart: **"New Quote
Request"** and **"New Driver Application"**.

**Attachments:** visitors can drag in, or tap to choose, **load photos and
documents** on the quote form and a **résumé** on the job application. The
limit is 10 MB total per submission. Phone photos are shrunk automatically so
they fit.

**What visitors see:** after they press send, the page hops to FormSubmit for a
second and comes right back with a "Got it" message.

**Status: activated.** Both forms use FormSubmit's private code for the inbox
(`formsubmit.co/c03892670506c031e28539ce68d933c4`), so the email address
itself isn't visible in the page code.

**To send forms to a different inbox later:**
1. In `index.html`, put the new email address in both
   `action="https://formsubmit.co/..."` lines.
2. Submit one test on the live site. FormSubmit emails the new inbox an
   **Activate** link (check spam); click it. That first test isn't delivered.
3. FormSubmit gives a new private code for that inbox. Put it in both
   `action` lines in place of the email address.

The email **shown** on the site (contact panel,
`richierichtransportationllc@gmail.com`) is separate. It only controls what
visitors see, not where forms are delivered.

> Tip: The first few emails may land in spam. Mark them "Not spam" so future
> ones go to the inbox.

---

## 🌐 2. The live site (GitHub Pages, free)

Live address: **https://richierichtransportation.com**
(the old `rolvera94.github.io/...` address redirects there automatically).

- **Keep the repository public.** GitHub's free plan only publishes public
  repositories; making it private takes the site offline.
- Changes merged into `main` go live within a minute or two. Merges you click
  yourself on GitHub deploy automatically. If a merge doesn't show up, go to
  **Settings → Pages** and click **Save** to trigger a fresh deploy.

---

## 📇 3. Common edits (all in `index.html`)

Search the file for the current text and type over it:

| To change...          | Search for...                            |
|-----------------------|------------------------------------------|
| Phone number          | `281.468.2201` (3 visible spots + links) |
| Email shown on site   | `richierichtransportationllc@gmail.com`  |
| Availability wording  | `Scheduling Available 7 Days a Week`     |
| USDOT number          | `4024817`                                |
| TXDMV registration    | `009730224C`                             |
| Coverage wording      | `Moving freight across Texas`            |

The copyright year updates itself every year.

---

## 🚚 4. Photos and the fleet

- The site **never lists how many trucks or trailers** we run. It presents a
  modern, growing fleet by capability (48 ft flatbeds, air-ride, tarps,
  chains and binders).
- The **Fleet** section and the **"You call Richard"** section use our **real**
  trucks. Keep those real.
- Six other photo slots use stand-ins until AI images are made. See
  **`IMAGE-PROMPTS.md`** for a ready-to-paste prompt and exact filename for
  each slot. Send the images to Claude and they'll be compressed and swapped in.

---

## 🔗 5. The domain: richierichtransportation.com

Bought at **GoDaddy** (renews yearly, about $10–25; keep auto-renew on or the
site goes offline). Hosting stays free on GitHub Pages.

How it's connected (don't change these unless moving hosts):
- **GoDaddy → DNS:** four **A** records for `@` pointing to `185.199.108.153`,
  `185.199.109.153`, `185.199.110.153`, `185.199.111.153`, and a **CNAME**
  for `www` pointing to `rolvera94.github.io`. `www.` redirects to the main
  address.
- **The `CNAME` file** in this repository contains `richierichtransportation.com`.
  It tells GitHub which domain to serve. **Don't delete it.**
- **GitHub → Settings → Pages:** custom domain set, **Enforce HTTPS** checked
  (the padlock).
- The email-related DNS rows at GoDaddy (`_domainkey`, MX) are separate and
  should be left alone.

### If a company's network blocks the site

Some business networks show "Your connection is not private"
(`NET::ERR_CERT_AUTHORITY_INVALID`) or a block page instead of the site. That's
the company's web filter, not the website. To confirm, click **Not secure →
Certificate is not valid** and read **Issued By**:
- **Let's Encrypt** (R10, R11, E5…) is the real certificate. Anything else, such
  as **NetAlerts** (DNSFilter), FortiGate or Zscaler, is the filter's.
- Fix for that office: their IT allowlists `richierichtransportation.com`.
- Fix for everyone on that filter: ask the filter company to rate the site as
  **Business / Transportation**. Most have a free public form.

Filters often block any domain under about 30 days old, so new-domain blocks
also clear with time.

---

## 📁 File overview

```
index.html         ← the entire website (text, layout, forms, Texas map)
images/            ← logo, truck photos, photo-slot images
IMAGE-PROMPTS.md   ← AI image prompts for each photo slot
robots.txt         ← helps Google find the site
sitemap.xml        ← helps Google index the site
HANDOFF.md         ← this guide
```
