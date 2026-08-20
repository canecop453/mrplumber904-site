# Website Handover — Mr. Plumber Remodel and More LLC

Everything needed to keep mrplumber904.com running, or to move it somewhere else.
Written so that any web developer can take over without contacting anyone.

**Last updated:** 2026-08-19 (launch)

---

## What this is

A static website. Plain HTML, CSS, and JavaScript — no WordPress, no database, no CMS, no
login. Every page is a file in this folder. Right now there is one page, `index.html`.

**What that means for you as the owner:** the site is extremely reliable and cheap to run.
It cannot be hacked the way WordPress sites are, and it needs no security updates. The
tradeoff is that there is **no dashboard where you can edit text yourself.** Changes are
made by editing files. Any web developer can do this; you cannot do it without one.

**What that means for a developer:** clone or download the folder, edit the HTML, deploy the
folder to any static host. There is no build step. There are no dependencies to install.

---

## What you own

| | |
|---|---|
| Domain name | `mrplumber904.com` — registered in Michael Rowland's name, at GoDaddy |
| Renews | Annually, on the owner's payment method |
| The website files | This repository / folder. Yours outright. |

**The domain is the only thing that is genuinely irreplaceable.** As long as it stays
renewed, everything else can be rebuilt. If you get a renewal notice, pay it.

---

## Where everything lives

| Thing | Where | Whose account |
|---|---|---|
| Domain registrar | GoDaddy (domain only, no other products) | Owner's |
| DNS | Cloudflare, free plan | Owner's, Jeremy has access |
| Website files | `canecop453/mrplumber904-site` on GitHub (public) | Jeremy's |
| Hosting | Zeabur, auto-deploys from `main` | Jeremy's |
| Contact form | Web3Forms — submissions email to `Mr.Plumber904@gmail.com` | Owner's inbox |
| Analytics | None yet | — |
| Search Console | None yet | — |
| Google Business Profile | **Not created yet — this is the biggest remaining gap** | Owner's, when created |

---

## Costs to keep it running

| | |
|---|---|
| Domain renewal | GoDaddy standard `.com` rate, once a year |
| Hosting | Free tier |
| Contact form | Free tier — 250 submissions per month |

---

## How updates get made

1. Edit the HTML files.
2. Push to the `main` branch on GitHub.
3. The host rebuilds automatically in about 30 seconds.

**No build step, no compile, no framework.** If you edit `index.html` and push it, that is
what goes live.

After a change, **hard refresh** to see it (Ctrl+Shift+R on Windows, Cmd+Shift+R on Mac).
Favicon changes are the exception — close the tab and reopen it.

---

## If something breaks

Work down this list. The first "no" is the broken layer.

1. Is the latest change visible on GitHub?
2. Does Zeabur show a recent successful deployment?
3. Does the staging URL `mrplumber904.zeabur.app` work? — this separates a hosting problem
   from a domain problem
4. Does the domain point where it should? — see DNS below
5. Only then suspect your browser's cache.

**Important fragility, in plain words:** the domain points at one specific server address
rather than at a name that can follow the server around. If the host ever changes that
address, the site will simply stop loading — with no warning, no error message, and
everything else still looking perfectly healthy. **If the site is down and nothing else
changed, check this first.** The address the domain should be pointing at is
`43.166.164.43`. Compare it against what Zeabur shows under Networking; if they differ,
update the two records below in Cloudflare and the site comes straight back.

### Current DNS records

| Type | Name | Value | Proxy |
|---|---|---|---|
| A | `@` | `43.166.164.43` | DNS only (grey cloud) |
| A | `www` | `43.166.164.43` | DNS only (grey cloud) |

Keep this table current. It is what lets anyone rebuild the setup from scratch.

**The grey cloud is deliberate** — turning on Cloudflare's proxy (orange cloud) interferes
with the host issuing the HTTPS certificate. Leave it off.

**DNS rollback:** setting the nameservers back to `ns77.domaincontrol.com` and
`ns78.domaincontrol.com` at GoDaddy reverts to registrar DNS.

---

## The contact form

The estimate form posts to Web3Forms, which forwards each submission by email to
`Mr.Plumber904@gmail.com`. There is no database and nothing to log into — the submissions
arrive as email and that is the only copy, so don't delete them.

The free tier covers 250 submissions per month. If the form ever goes quiet, check the
spam folder first.

---

## Moving to a different host

The site is a plain folder of files, so it runs on any static host.

**The easiest option for a non-technical owner is Cloudflare Pages** — free, and it accepts
a direct folder upload through the browser with no command line involved:

1. Create a free account at Cloudflare.
2. Workers & Pages → Create → Pages → **Upload assets**.
3. Drag this folder in.
4. Check the `*.pages.dev` address it gives you.
5. Add `mrplumber904.com` as a custom domain and update the DNS records.

GitHub Pages and Netlify also work. Any developer will have a preference; all of them are
fine.

*(Free-tier terms change — check current limits before relying on them.)*

---

## If you want to edit the site yourself

Be aware of what you're choosing. This site has no editing interface, and it isn't
practical to add one to a hand-built static site.

The realistic options:

- **Hire any web developer** for occasional changes. This is the cheapest path if changes
  are rare. Nothing here is unusual or proprietary — a developer can pick it up quickly.
- **Rebuild on a site builder** — Squarespace, Wix, or your registrar's builder — if you
  want to edit your own hours and prices at 9pm. You'd point `mrplumber904.com` at the new
  site and retire this one. **This is a perfectly reasonable choice**, not a step backward.

---

## Who built this

Jeremy — see the contact details supplied with the proposal.

If that contact is unreachable, everything a replacement developer needs is in this
document. Nothing here requires the original builder.
