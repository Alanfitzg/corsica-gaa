# Corsica GAA — next steps

Status: site cloned from Verona GAA and adapted for Corsica (FR / CO / EN, no
festival section, placeholder crest, Bonifacio hero, Corsica palette). Not yet
deployed.

## To go live

1. **Vercel:** import `Alanfitzg/corsica-gaa` as a new project (Add New → Project →
   import from GitHub). The first deploy gives a `*.vercel.app` URL.
2. **Storage:** Vercel → project → Storage → Create Database → Upstash Redis
   (free), connect it to the project. Credentials are injected automatically.
3. **Logins:** Settings → Environment Variables → `ADMIN_EMAILS` = comma-separated
   committee emails. Optional: `ANTHROPIC_API_KEY` for the translate button,
   `RESEND_API_KEY` + `SIGNUP_FROM_EMAIL` + `SIGNUP_NOTIFY_TO` for email alerts.
4. **Redeploy** after adding env vars.
5. **Domain:** add one under Settings → Domains when the club has picked a name.

## Content

- Real crest → `assets/crest.svg` (or `.png`, see README).
- Corsican copy reviewed by a speaker (`co` block in `i18n.js`).
- Confirm the Gaelic Games Europe wording (`gge.*` keys).
- Add photos of the first sessions to the games tiles when there are any.
