---
name: dropshipper
description: Use when the user wants to evaluate whether an online store is a dropshipper or dropshipping scam. Trigger on URLs to unfamiliar stores, questions about store legitimacy, or "is this site legit" type queries.
---

# Dropshipper Detection

Analyze an online store to determine whether it is a dropshipping operation and assess scam risk.

## How to Use

1. User provides a URL (or store name to look up)
2. Follow the investigation steps below, fetching multiple pages from the site
3. Score each signal from the checklist
4. Present a summary verdict with evidence

## Investigation Steps

1. **Fetch key pages** — use WebFetch on: homepage, a product page, About/Contact page, shipping policy, returns policy. Each fetch gives you raw signal.
2. **Check external reputation** — WebSearch for `"[store name]" review` and `"[store name]" scam`. Check Trustpilot, BBB, Reddit mentions.
3. **Reverse image search** — pick 2-3 product images (especially white-background shots) and search on Google Images or TinEye. Also try the AliExpress image search feature to find the same product at supplier prices.
4. **Search product descriptions** — copy a distinctive phrase from a product description, search it in quotes on Google. If it appears verbatim on AliExpress/Alibaba/DHGate, it's supplier copy.
5. **Compare prices** — search the product name or description on AliExpress. If the same item sells for 70-90% less, the store is dropshipping it.
6. **Check domain age** — run `whois [domain]` to see registration date. Young domains (< 1-2 years) combined with other signals add weight.

## Signal Checklist

Fetch the homepage, a product page, the About page, Contact page, shipping/returns policy, and terms of service. Score each signal as present (+1 toward dropshipper) or absent.

### Website Signals

| Signal | What to look for |
|--------|-----------------|
| **Shopify/generic platform** | Powered-by footer, `myshopify.com` in URLs, default theme with minimal customization |
| **Young domain** | WHOIS shows domain registered recently (< 2 years). Check via `whois` or WHOIS lookup |
| **No physical address** | No street address on Contact or About page; only a contact form or email |
| **No phone number** | No phone support listed anywhere on the site |
| **Generic About page** | Vague mission statements ("we bring you the best deals at the lowest prices") with no founder names, team photos, or real brand story |
| **Missing or thin policies** | No returns policy, no terms of service, or policies that are clearly template text |
| **Typos and poor writing** | Grammatical errors, inconsistent tone, machine-translated text |
| **Only product pages polished** | Product pages have effort; all other pages are bare or boilerplate |
| **No social proof beyond site** | No verifiable press mentions, no linked social media with real engagement |
| **Contact email is Gmail/Yahoo** | Business using free email provider instead of domain-based email |

### Product Signals

| Signal | What to look for |
|--------|-----------------|
| **Unrelated product mix** | Store sells unrelated categories (jewelry + garden tools + pet supplies) with no coherent brand |
| **AliExpress-style photos** | White-background product shots, lifestyle images with Chinese text or watermarks, identical photos across many sites |
| **Inconsistent photo styles** | Mix of professional studio shots, amateur photos, and stock images with different models — indicates sourcing from multiple suppliers rather than a single brand |
| **Huge catalog for a "small brand"** | Hundreds or thousands of products across unrelated categories for a brand nobody has heard of |
| **Copied descriptions** | Generic, verbose product descriptions that read like translated supplier copy. Search a unique phrase to see if it appears on AliExpress/Alibaba/Wish |
| **Extreme markups** | Products priced 3-10x above what identical items sell for on AliExpress/Amazon |
| **Suspiciously low prices** | Branded goods at far below market price (likely counterfeit) |
| **Always on "sale"** | Every product shows a crossed-out "original" price with a large discount |
| **Limited or no product variants** | Few size/color options compared to what a real retailer would stock |

### Shipping & Fulfillment Signals

| Signal | What to look for |
|--------|-----------------|
| **Long shipping times** | 2-6 weeks delivery, or "15-30 business days" — characteristic of ePacket/China Post |
| **Customs/duties disclaimer** | "Buyer is responsible for any customs or import duties" — signals international origin |
| **Multiple packages per order** | FAQ or policy mentions items may arrive in separate packages |
| **No return address** | Returns policy doesn't list a return address, or says "contact us for return authorization" |
| **Epacket/Yanwen/4PX tracking** | Tracking numbers from Chinese logistics carriers |

### Review & Trust Signals

| Signal | What to look for |
|--------|-----------------|
| **Fake on-site reviews** | All 5-star, generic praise, no verified purchase badges, reviews mentioning "seller" (copied from AliExpress) |
| **No external reviews** | No presence on Trustpilot, Google Reviews, BBB, or similar |
| **Suspicious Trustpilot** | Very few reviews, or clusters of positive reviews posted the same day |
| **Influencer-only marketing** | Products primarily advertised through social media influencers and targeted ads, with no organic presence |
| **Facebook/Instagram ad-driven** | Store found through social media ad rather than organic search |
| **Fake social media engagement** | High follower count but very low comments/likes, or comments are generic ("nice!" "love it!") with no real customer interaction |

### Payment & Security Signals

| Signal | What to look for |
|--------|-----------------|
| **No secure payment options** | Missing PayPal, Apple Pay, or major credit card processing |
| **Wire transfer/crypto only** | Requests unconventional payment methods |
| **Missing SSL details** | Certificate doesn't match company name or uses basic DV cert |

## Scoring

Count signals present and assess:

| Score | Verdict |
|-------|---------|
| 0-3 | **Unlikely dropshipper** — looks like a legitimate retailer |
| 4-7 | **Possibly dropshipping** — some red flags, recommend caution |
| 8-12 | **Likely dropshipper** — strong pattern of reselling supplier goods |
| 13+ | **Almost certainly dropshipping** — high scam risk, recommend avoiding |

## Verification Steps

When signals are ambiguous, try these:

1. **Reverse image search** product photos on Google Images or TinEye — if the same image appears on AliExpress/DHGate/Wish, it's dropshipped
2. **Search a product description phrase** in quotes on Google — if it appears on supplier marketplaces, it's copied
3. **Check WHOIS** for domain age and registrant info (privacy-protected registration alone isn't a red flag, but combined with other signals it adds weight)
4. **Search "[store name] review"** or "[store name] scam" on Google/Reddit
5. **Check Trustpilot/BBB** for the store name
6. **Compare prices** by searching the product title on AliExpress — if the same item exists for 80% less, the store is likely dropshipping it

## Important Nuances

**Dropshipping is not inherently a scam.** It's a fulfillment method where the store doesn't hold inventory. The scam is when stores use it to sell cheap products at extreme markups with no customer service or recourse.

**Some stores evolved past dropshipping.** Brands like Shein, Romwe, and CupShe started as dropshippers but now hold inventory and offer local shipping/returns. These aren't dropshippers anymore even though they sell cheap Chinese goods.

**Wholesale ≠ dropshipping.** A store that buys cheap goods from China in bulk, rebrands them, and ships locally from their own warehouse is not a dropshipper — they hold inventory and handle fulfillment.

**Savvy dropshippers hide it.** Some buy one sample to photograph with their own models, add custom branding to packages via their supplier, and build polished websites. No single signal is conclusive — look at the pattern across multiple signals.

## Output Format

Present findings as:

```
## Dropshipper Analysis: [Store Name]

**URL:** [url]
**Verdict:** [Unlikely / Possibly / Likely / Almost Certainly] dropshipper
**Confidence:** [Low / Medium / High]
**Signals found:** X of Y checked

### Evidence

- [Signal]: [specific evidence from the site]
- [Signal]: [specific evidence from the site]
...

### Recommendation

[Brief recommendation: safe to buy, proceed with caution, or avoid]
```

## Sources

Analysis methodology based on guidance from:
- BC Gov Information Security Branch — Drop Shipping Scams infosheet
- Chargeflow — How to Spot and Avoid Dropshipping Scams
- DoDropshipping — How to See if a Store is Dropshipping
- Michigan Consumer Protection — Before You Buy or Sell Online
- r/FrugalFemaleFashion — How to Tell if a Store is a Dropship Site
