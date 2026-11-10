# Margin — Project Status & Handoff

> **A paid digital product for resellers/flippers:** a profit tracker + playbooks that show
> them their *real* take-home after platform fees, and the tax write-offs they're missing.
> Tagline: **"Know what you keep."**

This document is a complete handoff for another AI agent or developer. It explains what
Margin is, what's built, and what's left to do. **Margin is a separate brand** from the
founder's free fitness app, *Day One* (different repo).

---

## 1. The vision (read this first)

**Audience:** resellers / flippers (sneakers, clothing, tickets, electronics) — people who
buy low and sell high on eBay, StockX, Depop, Poshmark, Mercari, Grailed, etc. This is a
**money/hustle audience**, not general consumers — they buy things that help them make or
keep money.

**The core insight / why anyone buys it:** most resellers confuse revenue with profit. They
think they made $72 on a flip; after fees + shipping they kept $36. And at tax time they
overpay because they never tracked their costs. Marketplace fees also change constantly and
nobody keeps up. **Margin sells clarity in a deliberately murky space** — the value is the
*knowledge* (correct, current fee tables + tax deductions), not just a spreadsheet they
could rebuild. That's what makes it survive the "I could do this myself" objection.

**Product = a Kit (a tool + guides), sold once.** Not a subscription.

---

## 2. Current status — what's DONE ✅

- **The tracker** (`product/tracker.html`) — a clean, single-file browser tool:
  - Add an item (cost, category, source, SKU, storage location, date).
  - Mark it sold → pick the platform and it **auto-applies the real fee** (e.g. eBay
    13.6% + $0.40, StockX ~12%, Depop ~3.3%+$0.45, etc.) → shows **true profit, ROI, and
    days-to-sell.**
  - Tracks **business expenses + mileage** and **lot/bundle cost-splitting** (buy 20 for
    $100 → splits across items).
  - Dashboard: net profit after fees & expenses, revenue, avg ROI, cash tied up.
  - **Tax-ready CSV export** with a Schedule-C-style summary.
  - Runs in any browser, saves on-device (localStorage), no account. Clean "financial
    ledger" design (serif headline, mono figures, green/red only on money).
- **Guide 01 — Fee & Margin Playbook** (`product/guide-01-fees.html` + PDF): current 2026
  fees per platform, a full fee matrix at multiple price points, when you actually get paid,
  break-even multipliers, "where to list what," a worked $2,000-month P&L.
- **Guide 02 — Reseller Tax & Deductions** (`product/guide-02-tax.html` + PDF): taxed on
  profit not sales, hobby vs business, the 1099-K, every deduction (COGS, fees, shipping,
  supplies, mileage, home office), a side-by-side return example, self-employment tax.
  Heavy "not tax advice / confirm with a pro" framing.
- **Guide 03 — Sourcing Playbook** (`product/guide-03-sourcing.html` + PDF): the 30-second
  buy check, where to source ranked by cash/effort/margin, what holds value vs traps,
  break-even math, avoiding fakes, a weekly routine.
- **Marketing kit:** `marketing/launch-pack.html` (offer, pricing, paste-ready storefront
  copy + FAQ, a 35-second demo-video script, zero-budget distribution plan) and
  `marketing/tiktok-pack.html` (12 hooks, 4 scripts, captions, content pillars).
- **Brand & storefront graphics:** `marketing/` — a storefront banner, product thumbnail,
  and profile avatar. Brand = wordmark "Margin" (Fraunces serif) + an ascending-bars mark,
  money-green on warm charcoal, tagline "Know what you keep."

Everything is built and polished. **Margin has not been listed for sale yet.**

---

## 3. Repository structure

```
margin/
├─ README.md                      ← this file
├─ product/                       ← what the buyer gets (the Kit)
│   ├─ tracker.html               ← the profit tracker tool
│   ├─ guide-01-fees.html / .pdf  ← Fee & Margin Playbook
│   ├─ guide-02-tax.html / .pdf   ← Reseller Tax & Deductions
│   └─ guide-03-sourcing.html/.pdf← Sourcing Playbook
└─ marketing/                     ← selling it
    ├─ launch-pack.html           ← offer, pricing, storefront copy, demo script, distribution
    ├─ tiktok-pack.html           ← hooks, scripts, captions
    ├─ storefront-banner.png
    ├─ product-thumbnail.png
    └─ profile-avatar.png
```

The tracker and guides are plain self-contained HTML (deliver the tracker as the `.html`
file; the guides are also provided as PDFs for selling). No build step, no dependencies
except Google Fonts.

---

## 4. Where to sell & pricing

- **Whop was abandoned** (setup friction, and its audience fit was shaky). **Do not use Whop.**
- **The founder already has Payhip** — use that as the checkout. Also good: **Etsy** (real
  search traffic — people literally search "reseller spreadsheet"; frame the Kit as a
  "profit spreadsheet + guides"), and **Gumroad** (built-in Discover). The founder promotes
  from a **personal TikTok**, so a link-in-bio store matters more than marketplace discovery.
- **Pricing:** launch the full Kit at **~$12, anchored against ~$29** (shown as a crossed-out
  price). The first ~20 sales are for **reviews, not profit** — with no audience you're
  pricing the risk a stranger takes on you. Once there are ~15+ reviews, raise toward $19–24.
- **Funnel:** consider giving the **tracker free** as a lead magnet and selling the full Kit
  (tracker + 3 guides) — the free tool builds trust, then upsells. (This is optional; the
  current packaging is a single paid Kit.)

Full positioning, pricing logic, storefront copy, FAQ, demo-video script, and the
value-first distribution plan are in `marketing/launch-pack.html`.

---

## 5. What's LEFT to do 🔧

1. **Create the Payhip product(s)** — upload the tracker `.html` + 3 guide PDFs; set price
   ($12, anchored $29); paste the listing copy/FAQ from the launch pack.
2. **(Optional) List on Etsy + Gumroad** for extra discovery; Etsy especially for search.
3. **Record the 35-second demo video** (script is in the launch pack) — this is the #1
   marketing asset; post it from the personal TikTok.
4. **Run the zero-budget distribution plan** — value-first in reseller communities
   (r/Flipping, r/Resell, reseller Discords) + TikTok/Reels/Shorts + Pinterest. **Never
   spam paid links** (communities ban it); lead with genuine help / the free tool.
5. **Collect reviews, then raise the price.**
6. **Keep the fee + tax numbers current** — they're dated and carry "verify" notes, but
   marketplace fees and tax thresholds change; refresh every few months so the product stays
   accurate (this accuracy is the whole value prop).

---

## 6. Key decisions & gotchas for the next agent

- **The value is embedded knowledge, not the tool.** Keep the fee tables and tax info
  *accurate and current* — that's what justifies the price and beats "I'll just use a free
  spreadsheet." Stale numbers kill the product.
- **Always frame tax content as general education, not advice** ("confirm with a tax
  professional / IRS.gov"). Legal/liability matters.
- **Audience = money/hustle, reachable in reseller communities & on TikTok.** Match copy to
  that audience (making/keeping money), not general consumers.
- **Distribution is the real constraint**, not the product. With no audience, the plan is
  value-first participation + short video + (ideally) a free lead magnet. Don't rely on a
  marketplace to find buyers.
- **On-device, no backend** — the tracker stores everything in the browser; keep it that way
  (zero cost, private). CSV export is the backup mechanism.

---

*Generated as a handoff snapshot. `product/` is what sells; `marketing/` is how it sells.*
