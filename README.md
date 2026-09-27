# Swarna's Food Court — website

One file, no build step: `index.html` holds the menu, prices (₹), WhatsApp ordering and the "Find us" section.

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

- `price` is in rupees.
- `veg: true` shows the green vegetarian mark; `false` shows the non-veg mark.
- `img` picks the plate artwork: biryani, friedrice_c, friedrice_v, noodles_c, noodles_v, manchuria, chicken65, kebab, pakodi, fish, boneless, roti.
- To show a real photo, upload it to an `images/` folder and add `photo: "images/biryani.jpg"` to the dish.
- To add a category, add a new `{ name: "…", items: [ … ] }` block.

## Custom domain (optional)

Settings → Pages → Custom domain, then add the DNS records GitHub shows you.
