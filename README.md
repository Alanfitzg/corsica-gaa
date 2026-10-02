# Corsica GAA — landing page

A trilingual (French / Corsican / English) landing page for a new GAA club and
community forming in Corsica, France. Static site — no build step, no
dependencies — plus a handful of serverless functions for sign-ups and a private
committee dashboard. Cloned from the Verona GAA site.

## Files

| File | Purpose |
|---|---|
| `index.html` | Page structure and content |
| `styles.css` | Theme + layout. **Edit the colour variables at the top to match the crest.** |
| `i18n.js` | All FR / CO / EN copy (the `data-i18n` keys) |
| `script.js` | Language toggle (FR → CO → EN) + form handling |
| `assets/crest.png` | Club crest (mouflon); `favicon.png` and `apple-touch-icon.png` are cut from it |
| `assets/corsica-hero.jpg` | Hero photo (Genoese tower at Porto, CC BY-SA 3.0, Myrabella) |
| `admin.html` | Committee dashboard, served at `/admin` |
| `api/*.js` | Vercel functions: sign-ups, questions, mailing list, dashboard data, translation |
| `ADMIN-SETUP.md` | How to provision storage, logins and the optional translate button |

## Run it locally

Just open `index.html` in a browser, or serve the folder:

```bash
cd ~/corsica-gaa
python3 -m http.server 8000
# then visit http://localhost:8000
```

(The forms and `/admin` need the Vercel functions, so they only work once deployed
or under `vercel dev`.)

## Before launch

1. **Crest.** In place: `assets/crest.png` (transparent background, 480px wide),
   with `favicon.png` and `apple-touch-icon.png` cut from the same artwork. To
   change it, replace those three files and keep the names.
2. **Colours.** Set `--brand`, `--brand-2`, `--accent` at the top of `styles.css` to
   the crest colours.
3. **Corsican copy.** The `co` block in `i18n.js` was drafted without a native
   speaker — have it checked.
4. **Gaelic Games Europe wording.** The site says the club is "being set up within
   Gaelic Games Europe". Adjust `gge.body` and `gge.kicker` in `i18n.js` once the
   affiliation status is confirmed.
5. **Deploy.** Import the GitHub repo into Vercel, then follow `ADMIN-SETUP.md` for
   the database, the committee logins and the optional translate button.
