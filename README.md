# Smart Daraz Shopper

An affiliate content site giving practical shopping guidance for Daraz —
spotting fakes, reading seller signals, getting real deals, and knowing your
return rights. Plain HTML/CSS, no build step, no dependencies.

## Deployment

To be pushed to GitHub and hosted on GitHub Pages, same setup as
[smb-security-stack](../smb-security-stack/README.md):

```bash
git init
git add -A
git commit -m "Initial site"
git branch -M main
gh repo create smart-daraz-shopper --public --source=. --remote=origin
git push -u origin main
gh api -X PUT repos/itsmaheenb-code/smart-daraz-shopper/pages -f "build_type=legacy" -f "source[branch]=main" -f "source[path]=/"
```

Once live at `https://itsmaheenb-code.github.io/smart-daraz-shopper/`, every
push to `main` auto-deploys within ~30-60 seconds.

## Monetization: the Daraz Affiliate Program

This site is written to eventually carry Daraz affiliate links, but **the
affiliate program itself requires an active site with real content and
traffic before approval** — so get this live and let a few posts sit for a
bit before applying.

1. Go to the [Daraz Affiliate Program](https://www.daraz.pk/affiliate-program/)
   page and sign up — this needs your name, contact details, and information
   about where you'll promote (this site's URL). I can't create this account
   for you; it needs your identity info.
2. Approval typically takes 1-7 business days.
3. Once approved, Daraz's affiliate dashboard generates trackable links per
   product or category. Add these to relevant posts, replacing any
   `<!-- AFF:description -->`-marked placeholders.
4. Reported commission is up to ~11% depending on category — confirm current
   rates in the affiliate dashboard once approved, they vary and change.

## Adding new content

Follow `CONTENT-PLAYBOOK.md` — exact structure, style rules, and a topic
backlog so new posts stay consistent with the first three.

## Legal basics already handled

- `disclosure.html` — affiliate disclosure, worded to reflect that
  monetization isn't active yet (see conversation history / decision: keep
  the disclosure present at all times once any affiliate program is the
  plan, since removing it risks forgetting to re-add it the moment real
  links go live).
- Every post carries the disclosure note near the top, not just the footer.

Still worth doing before real traffic: replace the placeholder contact email
in `disclosure.html` with a real one.
