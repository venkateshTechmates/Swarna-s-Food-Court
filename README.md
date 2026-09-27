# Swarna's Food Court — website

A static site with no server and no build step. `index.html` holds the menu, prices (₹), WhatsApp ordering and the "Find us" section. Orders are not stored anywhere; they are sent to the shop as a WhatsApp message.

| File | Purpose |
|---|---|
| `index.html` | The whole site |
| `images/` | Dish photos, app icons and the share preview banner |
| `404.html` | Shown for a wrong link, points back to the menu |
| `manifest.webmanifest` | Lets customers add the site to their phone home screen |
| `sitemap.xml` | For Google Search Console |

**Live site:** https://venkateshtechmates.github.io/Swarna-s-Food-Court/

## Turn on GitHub Pages (one time)

1. Open the repository on github.com, then **Settings → Pages**.
2. Under **Build and deployment → Source**, choose **GitHub Actions**.
3. Open **Actions → Deploy to GitHub Pages → Run workflow** (or push any commit).
4. After about a minute the site is live at the address above.

Every later commit to `main` redeploys automatically.

> If the Pages deploy is refused with "Branch is not allowed to deploy", open
> **Settings → Environments → github-pages** and add the branch you pushed to,
> or merge into `main`.

## Contact details

| | |
|---|---|
| Phone / WhatsApp | +91 99598 19651 |
| Phone | +91 90008 49023 |
| Email | swornarojesh@gmail.com |

These live in the `CONFIG` block near the top of the `<script>` in `index.html`:

```js
whatsapp: "919959819651",                    // country code + number, digits only
phones: ["+919959819651", "+919000849023"],  // first one is used by the Call buttons
email: "swornarojesh@gmail.com",
hours: "Open daily, 11 am to 11 pm",
```

Set `whatsapp: ""` to make the order button share or copy the order text instead.

## Change prices or dishes

Edit the `MENU` array in the same `<script>`. Each dish is one line:

```js
{ id: "cdb", name: "Chicken Dum Biryani", price: 120, veg: false, img: "biryani", desc: "…" }
```

- `price` is in rupees. `price: null` shows "Ask price"; the dish can still be ordered and the WhatsApp message says "price at counter". Chicken Lollipop and Tandoori Chicken are set this way until their prices are filled in.
- `veg: true` shows the green vegetarian mark; `false` shows the non-veg mark.
- `img` picks the dish photo from the `images/` folder: biryani, friedrice_c, friedrice_v, noodles_c, noodles_v, manchuria, chicken65, kebab, pakodi, lollipop, tandoori, fish, boneless, roti.
- To use a different photo, upload it to `images/` and add `photo: "images/my-photo.jpg"` to the dish.
- To add a category, add a new `{ name: "…", items: [ … ] }` block.

## Photos

The dish photos in `images/` were cropped from the shop's two posters. `images/banner.jpg` is the preview picture shown when the link is shared on WhatsApp.

## Get found on Google (optional)

1. Open https://search.google.com/search-console and add the site address as a URL-prefix property.
2. Verify it, then submit `sitemap.xml` under **Sitemaps**.
3. Also claim the shop on Google Business Profile and put the site address in it.

## Custom domain (optional)

Settings → Pages → Custom domain, then add the DNS records GitHub shows you.
