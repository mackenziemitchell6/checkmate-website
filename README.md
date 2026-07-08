# CheckMate marketing & legal site

Plain HTML + CSS, no build step, no framework, no dependencies. Five pages
sharing one stylesheet (`assets/style.css`) and one favicon
(`assets/favicon.svg`).

```
/
├── index.html      Landing page (marketing URL)
├── support.html    Support page (support URL)
├── privacy.html    Privacy Policy (privacy policy URL)
├── terms.html      Terms of Service
├── contact.html    Contact page
└── assets/
    ├── style.css
    └── favicon.svg
```

## Why plain HTML instead of Next.js/React

For a five-page static site with no dynamic data, no forms with backend
logic, and no CMS, a framework adds a build step, a `node_modules` tree, and
future upgrade burden for zero functional benefit. Plain HTML:

- Loads faster (no JS framework to download/hydrate)
- Has nothing to break on a dependency bump
- Is deployable anywhere, instantly, for free
- Is trivially editable by anyone who can edit a text file

If you later want a blog, a changelog, or localized pages, Next.js
(deployed to Vercel) is the natural upgrade — the copy in these files
ports over directly, just wrapped in components.

## Deploying

Any static host works. Three good free options:

**Vercel** — `npx vercel` from this directory, or connect the repo in the
Vercel dashboard and set the root directory to this folder. Zero config
needed (no `vercel.json` required for a plain static site).

**Netlify** — drag this folder into the Netlify dashboard, or connect the
repo and set the publish directory to this folder.

**Cloudflare Pages** — connect the repo, framework preset "None," build
command empty, output directory `/`.

All three give you free HTTPS, a global CDN, and a `*.vercel.app` /
`*.netlify.app` preview URL immediately — point your real domain at it
once you're ready.

## Launch checklist

**Done:**
- Domain wired in: `checkmatesplit.app` (canonical links + Open Graph/Twitter URLs across all pages)
- Governing law set to the Commonwealth of Massachusetts (`terms.html` §10)
- Social icons removed from footers and the contact page (no real accounts yet — add them back in `assets/style.css`'s `.social-row` + the footer markup once you have real handles, rather than linking to accounts that don't exist)

**Still placeholder — search for these strings and replace them:**

| Placeholder | Where | Replace with |
|---|---|---|
| `apps.apple.com/app/idXXXXXXXXXX` | `index.html` (two buttons) | Your real App Store URL once the app is approved |
| `support@checkmate.app` | `support.html`, `contact.html`, footers | Your real support inbox |
| `privacy@checkmate.app` | `privacy.html`, `contact.html` | Your real privacy inbox (can be the same as support) |
| `legal@checkmate.app` | `terms.html` | Your real legal inbox (can be the same as support) |
| `partnerships@checkmate.app`, `press@checkmate.app` | `contact.html` | Real inboxes, or point both at support if you don't need to split them yet |
| `[Month Day, Year]` | `privacy.html`, `terms.html` | The date you actually publish these |
| `assets/og-image.png` | Open Graph tags in every page | A real 1200×630 social preview image (referenced but not yet created — see below) |

Emails were deliberately left as placeholders (at your call) until you've
set up real inboxes — note they're still on the `@checkmate.app` domain,
not `@checkmatesplit.app`, so update the domain too whenever you fill
these in for real.

**Also still missing, not placeholders:**
- Real app screenshots to replace the gray `phone-shot`/`wide-shot` boxes throughout `index.html`
- An actual `assets/og-image.png` (1200×630px) for social link previews
- A real legal entity name if you've incorporated (currently the policies just say "CheckMate")

## Additional pages worth adding before/soon after launch

Not required by Apple, but worth having:

- **`/status`** or a status-page.io style page, once you have real uptime to report
- **`/press`** — a simple press kit (logo files, one-paragraph company description) once press inquiries start
- **Cookie/tracking disclosure** — only needed if you add a web analytics script to this *site* (the mobile app's analytics are already covered in the Privacy Policy)
- **A real testimonials/reviews section on the homepage** — intentionally left out for now rather than faked; add real App Store reviews once you have them, not before
