# RichieRich Transportation LLC — Website Handoff Guide

This is a simple, single-page website. Everything lives in one file (`index.html`)
plus an `images/` folder. There is no database, no monthly hosting bill, and
nothing to log into day-to-day. This guide covers the few things you need to know.

---

## ✅ 1. REQUIRED before the forms will work (5 minutes, free)

Right now the "Request a Quote" and "Careers" forms are built but **not yet
connected**. Until this step is done, submitting a form just tells the visitor to
call. To make submissions email straight to the Gmail inbox:

1. Go to **https://web3forms.com**
2. In the box, enter the email: **richierichtransportationllc@gmail.com**
3. Web3Forms will email that address a free **Access Key** (looks like
   `abc12345-6789-...`). Open the email and confirm it.
4. Open `index.html`, find this line near the bottom (inside the `<script>` section):

   ```js
   const WEB3FORMS_KEY = "REPLACE_WITH_YOUR_WEB3FORMS_ACCESS_KEY";
   ```

5. Replace `REPLACE_WITH_YOUR_WEB3FORMS_ACCESS_KEY` with your real key (keep the quotes).
6. Save and re-upload/commit. Done.

**That's it.** Every quote request and driver application will now land in the
Gmail inbox above — free, unlimited, forever. No account to manage.

> Tip: After connecting it, submit a test through each form and confirm the email
> arrives (check spam the first time and mark it "Not spam").

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
