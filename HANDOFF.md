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

**One-time setup (do this once, right after the site goes live):**
1. Submit one test quote on the live site.
2. FormSubmit emails **richard18olvera@gmail.com** an **"Activate Form"** message
   (check spam). Click **Activate**. That first test won't be delivered; every
   submission after activation will be.
3. FormSubmit then offers a **random string** (letters and numbers) you can use
   instead of the email address. Send it to Claude. It replaces the plain email
   address in the page code so spammers can't read the address there.

**To send forms to a different inbox later:** replace the email/alias in both
`action="https://formsubmit.co/..."` lines in `index.html`, then activate the
new inbox the same way.

The email **shown** on the site (contact panel,
`richierichtransportationllc@gmail.com`) is separate. It only controls what
visitors see, not where forms are delivered.

> Tip: The first few emails may land in spam. Mark them "Not spam" so future
> ones go to the inbox.

---

## 🌐 2. The live site (GitHub Pages, free)

Live address: **https://rolvera94.github.io/RichieRich-Transportaion-Website/**

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
| Business hours        | `6am – 8pm`                              |
| USDOT number          | `4024817`                                |
| TXDMV registration    | `009730224C`                             |
| Coverage wording      | `Moving freight across Texas`            |

The copyright year updates itself every year.

---

## 🚚 4. Photos and the fleet

- The site **never lists how many trucks or trailers** we run. It presents a
  modern, growing fleet by capability (48–53 ft flatbeds, air-ride, tarps,
  chains and binders).
- The **Fleet** section and the **"You call Richard"** section use our **real**
  trucks. Keep those real.
- Six other photo slots use stand-ins until AI images are made. See
  **`IMAGE-PROMPTS.md`** for a ready-to-paste prompt and exact filename for
  each slot. Send the images to Claude and they'll be compressed and swapped in.

---

## 🔗 5. Custom domain later (optional, about $10–13/year)

The free `github.io` address works fine. For something like
`richierichtransportation.com`:

1. Buy the domain (Namecheap, Cloudflare, etc.).
2. GitHub → Settings → Pages → **Custom domain**, enter it.
3. At the domain registrar, add the DNS records GitHub shows you.
4. Check **Enforce HTTPS** once it's ready.
5. Ask Claude to update the site address in `index.html`, `sitemap.xml`, and
   `robots.txt`.

The domain is the only part that isn't free; hosting stays $0.

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
