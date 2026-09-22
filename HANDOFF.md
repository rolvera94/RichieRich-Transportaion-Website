# RichieRich Transportation LLC — Website Handoff Guide

This is a simple, single-page website. Everything lives in one file (`index.html`)
plus an `images/` folder. There is no database, no monthly hosting bill, and
nothing to log into day-to-day. This guide covers the few things you need to know.

---

## ✅ 1. Forms — connected

The "Request a Quote" and "Careers" forms are connected through **Web3Forms**
(free, unlimited). Every submission is emailed to **richard18olvera@gmail.com**.
Subject lines tell them apart: **"New Quote Request"** and **"New Driver
Application"**.

**To send forms to a different inbox later**, do either of these:
- Log in at **https://web3forms.com** and change the email on the
  "RichieRich Website" form, **or**
- Create a new key for the new inbox and replace the key in `index.html`
  (search for `WEB3FORMS_KEY`; keep the quotes).

The email **shown** on the site (contact section and footer,
`richierichtransportationllc@gmail.com`) is separate. It only controls what
visitors see, not where forms are delivered.

> Tip: The first few emails may land in spam. Mark them "Not spam" so future
> ones go to the inbox.

---

## 🌐 2. Making the site live (GitHub Pages — free)

The site is hosted for free through GitHub Pages.

1. On GitHub, open the repository → **Settings** → **Pages**.
2. Under "Build and deployment", set **Source: Deploy from a branch**.
3. Choose branch **`main`** and folder **`/ (root)`**, then **Save**.
4. Wait ~1 minute. Your live address will be:

   **https://rolvera94.github.io/richierich-transportaion-website/**

Any time you change `index.html` on the `main` branch, the live site updates
automatically within a minute or two.

---

## 📇 3. Common edits (all in `index.html`)

You can change these by searching the file for the current text and typing over it:

| To change...        | Search for...                          |
|---------------------|----------------------------------------|
| Phone number        | `281.468.2201` (appears in a few spots)|
| Email               | `richierichtransportationllc@gmail.com`|
| Business hours      | `6am – 8pm CT`                         |
| USDOT number        | `4024817`                              |
| TXDMV registration  | `009730224C`                           |
| Service area states | search for `state-cell`                |

The copyright year at the bottom updates itself automatically each year — no edit needed.

---

## 🚚 4. About the "Equipment & Fleet" section

This section highlights the quality and standard of the equipment (flatbeds,
securement, what we haul) **without listing a specific number of trucks** — so it
reads as an established, capable operation. The two truck photos are used as
showcase imagery. To swap a photo, replace the file in the `images/` folder
(keep the same filename) or update the `src="images/..."` line.

---

## 🖼️ 5. Adding more Houston photos to the slideshow

The "Our Story" section has an auto-playing Houston photo slideshow. It now
**manages itself** — to add a photo you only add one line; the little navigation
dot appears automatically.

**Steps:**
1. Download a photo (see the free, commercial-use-OK list below).
2. Save it into the `images/` folder, e.g. `images/Houston Night.jpg`.
3. In `index.html`, find `<div class="houston-track">` and add one line inside it:
   ```html
   <img class="houston-slide" src="images/Houston Night.jpg" alt="Downtown Houston at night" />
   ```
4. Save. Done — the slideshow now includes it.

**Free Houston photos (safe for a business website — free for commercial use, no
attribution required).** Open each link and click "Free Download":

| Photo | Link |
|-------|------|
| Downtown Houston skyline at night (aerial) | https://www.pexels.com/photo/aerial-view-of-downtown-houston-texas-at-night-15353653/ |
| Houston skyline over Buffalo Bayou | https://www.pexels.com/photo/modern-skyline-overlooking-houston-s-buffalo-bayou-37406430/ |
| Buffalo Bayou at twilight, downtown | https://www.pexels.com/photo/scenic-view-of-buffalo-bayou-in-houston-texas-37106432/ |
| More options (search page) | https://www.pexels.com/search/houston%20skyline/ |

> Best of all: **your own photos of Houston, the trucks, or loads** work great here
> and make the site more personal. Just drop them in `images/` and add the line above.

**Two sources that are always free for commercial use:**
[Pexels](https://www.pexels.com) and [Unsplash](https://unsplash.com). Avoid pulling
images from a Google image search — those are often copyrighted.

---

## 🔗 6. Custom domain later (optional, ~$10–13/year)

The free `github.io` address works great to start. If you later want something
like `richierichtransportation.com`:

1. Buy the domain (Namecheap, Cloudflare, Google Domains, etc.).
2. In GitHub → Settings → Pages → "Custom domain", enter your domain.
3. At your domain registrar, add the DNS records GitHub shows you.
4. Check "Enforce HTTPS" once it's ready.

The domain is the only part that isn't free — hosting stays $0.

---

## 📁 File overview

```
index.html      ← the entire website (text, layout, forms)
images/         ← logos, truck photos, Houston photos
robots.txt      ← helps Google find the site
sitemap.xml     ← helps Google index the site
HANDOFF.md      ← this guide
```

Questions or changes down the road — everything is in that one `index.html` file.
