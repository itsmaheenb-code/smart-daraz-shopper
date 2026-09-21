# Content playbook

How new posts get added to this site — follow this exactly so every post matches
in structure, tone, and honesty about what is/isn't affiliate-linked. Written so
either Michelle or a future Claude Code session (manual or scheduled) can
produce a consistent post from it.

## Process for one new post

1. **Pick a topic** from the backlog below (or a new one that fits the same
   pattern: practical "how to shop smart on Daraz" guidance — not a review of
   one specific product, but a buying-behavior or platform-mechanics topic).
2. **Research current facts with web search** — Daraz's policies change
   (return windows, voucher mechanics, sale-day names), so don't reuse a fact
   from an old post without reverifying it's still accurate.
3. **Write the post** using `posts/how-to-spot-fake-products-on-daraz.html`
   as the exact structural template:
   - Header with logo badge: `<span class="logo-badge">D</span>Smart Daraz Shopper`.
   - Right after `<main>`, a `<span class="post-tag tag-X">Category</span>` —
     reuse an existing tag class (`tag-safety`, `tag-deals`, `tag-sellers`,
     `tag-returns`, `tag-payments`) if the topic fits, or add a new
     `.tag-newcategory` rule to `assets/style.css` using an existing color
     variable if it doesn't.
   - One `<div class="tool-card"><h2>...</h2><span class="price-chip">...</span>
     <p>...</p></div>` per tip/step (3-4 per post). The `price-chip` span is a
     small label, not necessarily a price — use it for things like "Free
     signal", "Red flag check", "2-minute check". Add class `warn` for a
     caution-toned chip or `gold` for a highlight-toned one.
   - A closing `<div class="verdict-box"><h2>The short version</h2><p>...</p>
     </div>` that summarizes the practical takeaway in a few sentences.
   - FAQ as `<details class="faq-item"><summary>Question?</summary><p
     class="faq-answer">Answer.</p></details>` — 3-4 questions, phrased the
     way someone would actually type or ask an AI assistant.
   - Article + FAQPage JSON-LD in `<head>` matching the visible content
     exactly, `<meta name="author">`, `<link rel="canonical">` using
     `https://itsmaheenb-code.github.io/smart-daraz-shopper/posts/<slug>.html`,
     and a visible byline with a real `<time datetime="YYYY-MM-DD">`.
4. **Don't fabricate hands-on experience** ("I bought this and...") — this
   site gives shopping guidance based on Daraz's published policies and
   general best practice, not first-hand product reviews. Say so if relevant.
5. **Affiliate links**: once the Daraz Affiliate Program is approved, product
   or category links can be added using the affiliate tracking format Daraz's
   dashboard provides. Until then, don't add product links that imply
   monetization is active — general guidance content doesn't need them to be
   useful. Mark any pending ones with `<!-- AFF:description -->` before the
   link, same convention as our other site.
6. **Add the post to `index.html`**'s post-grid (top of the list, most recent
   first) and to `sitemap.xml`.
7. **Commit and push**: `git add -A && git commit -m "Add post: <title>"`.
   Auto-deploys via GitHub Pages — nothing else needed.

## Haul posts (a different, real-first-person content type)

Alongside the evergreen guides above, this site also carries **haul posts** —
Michelle's own real Daraz orders, with her own photos and honest opinions.
These are the one place on the site where first-person "I bought this and
here's what I think" framing is not only allowed but the whole point —
unlike the evergreen guides, which explicitly avoid claiming hands-on testing
that didn't happen. Don't blend the two styles.

**Workflow:**
1. Michelle sends photos of what she ordered + the price paid + her honest
   take per item (worth it, quality, sizing, any issues) + ideally the Daraz
   product link for each.
2. Save her photos into `assets/hauls/<slug>/` (create the folder).
3. Copy `templates/haul-post-template.html` to `posts/<slug>.html` and fill
   in every placeholder — title, date, one `.haul-item` per product using
   her real photo paths, her real prices and her real words for the "take,"
   not invented copy.
4. Tag it `<span class="post-tag tag-hauls">Haul</span>`.
5. Add it to `index.html`'s post-grid and to `sitemap.xml`, same as any post.
6. If a product link is available and the Daraz Affiliate Program is
   approved, use the real affiliate link; otherwise mark it
   `<!-- AFF:describe-product -->` pointing at the plain product URL, same
   convention as the rest of the site.
7. Commit and push.

Never write a haul post from scratch without her actual photos/details —
fabricating a "haul" she didn't really do would be dishonest and is exactly
the kind of fake-experience content the rest of this playbook explicitly
warns against for the evergreen guides. If a scheduled/automated run reaches
this point in the backlog with no haul material provided, skip haul content
that cycle and write an evergreen guide instead.

## Topic backlog (rough priority order)

- Daraz return & refund process explained step by step (marketplace vs. DarazMall windows, what voids a return)
- How Daraz Cash on Delivery vs. online payment actually compares (safety, speed, when to pick which)
- How to track a Daraz order and what the status labels actually mean
- Daraz Wallet explained: what it is, when it's worth using
- How to avoid common Daraz scams (fake delivery calls, phishing links, off-platform payment requests)
- How to actually use Daraz reviews to judge a product (photo reviews vs. text-only, verified purchase tags)

Keep adding to this list as Daraz's policies or features change — verify
before generating from it.

## Style notes

- Second person, direct, practical — no filler intros.
- Every post needs the disclosure note near the top, not just the footer.
- Comparison tables where genuinely useful (e.g. return windows by seller
  type); tip cards for step-by-step or checklist-style content.
- Don't overstate risk ("Daraz is full of scammers") — most listings are
  fine; the goal is teaching a quick, real filter, not generating anxiety.
