# slatepointtech.com

Single-page static site for Slate Point Technologies: stormwater compliance
software for California construction firms.

## Structure

- `index.html` is the entire site (HTML + CSS inlined for zero-config deploy)
- No JavaScript, no build step, no dependencies.

## Deploy (recommended: Vercel)

Fastest path from zero to live at slatepointtech.com:

1. Push this directory to a new GitHub repo:
   ```bash
   cd /Users/justin/code/slatepoint-tech
   git init && git add -A && git commit -m "initial site"
   gh repo create slatepoint-tech --public --source=. --push
   ```
2. Go to https://vercel.com, sign in with GitHub, click **Import Project**, pick
   `slatepoint-tech`. Vercel auto-detects a static site. Click Deploy.
3. Vercel gives you a `.vercel.app` URL that works immediately.
4. In Vercel → Project → Settings → Domains, add `slatepointtech.com` and
   `www.slatepointtech.com`.
5. At your domain registrar (where you bought slatepointtech.com), update DNS:
   - `A` record for `@` → Vercel's IP (Vercel shows the exact value)
   - `CNAME` for `www` → `cname.vercel-dns.com`
6. SSL provisions automatically within a few minutes.

**Cost:** Free on Vercel's Hobby tier. No credit card needed.

## Alternatives if you prefer

- **Cloudflare Pages** (https://pages.cloudflare.com): same experience as
  Vercel, free, slightly faster global CDN. Good choice if you'd rather keep
  DNS at Cloudflare.
- **Netlify** (https://netlify.com): equivalent to Vercel, same workflow.
- **GitHub Pages**: free, but the DNS/domain setup is clunkier and redeploys
  are slower.
- **Carrd**: if you want to manage content through a visual editor instead of
  editing HTML. $9/year. Would require rebuilding the page in their editor.

## Email: set up Google Workspace before sending outreach

You'll want `justin@slatepointtech.com` before the cold emails go out:

1. https://workspace.google.com. **Business Starter, $6/mo**.
2. Sign up with slatepointtech.com as the domain.
3. Google guides you through DNS MX records at your registrar.
4. Once verified, you can send from `justin@slatepointtech.com` (and the site's
   `mailto:` link will route there automatically).

**Alternative, free:** Use email forwarding from your registrar. Most let you
forward `justin@slatepointtech.com` to your Gmail for free. But replies will
go from `justinjsumner@gmail.com`, which hurts reply rates on cold outreach.
Worth the $6/mo to send from your domain.

## Editing later

Everything is in `index.html`. To change copy, just edit and redeploy. Vercel
auto-deploys on every `git push`.

Adding a Calendly link: search for `mailto:justin@slatepointtech.com` in
`index.html` and replace those `href` values with your Calendly URL. There are
two: one in the nav bar and one in the bottom CTA block.
