---
name: drop-shipper-analysis
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
| **City name mismatch** | Store name includes a city (e.g. "Lumina Vancouver") but WHOIS, shipping origin, or return address point somewhere else entirely — a deliberate attempt to borrow credibility from a trustworthy locale |
| **No clear refund/support page** | No dedicated support page, or the refund policy is buried, vague, or hidden behind a contact form. Legitimate retailers explain return windows, who pays return shipping, and the return address in plain language |

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

## EU Regulations

If the seller targets customers in the European Economic Area (EEA) — which includes having an EEA-language site, EEA domain, or advertising in an EEA country — two EU directives likely apply, regardless of where the seller is physically located. A customer complaining about a dropshipper in this context can often point to specific violations.

### Consumer Rights Directive (2011/83/EU)

Governs distance contracts (online sales). Key rights:

- **14-day right of withdrawal.** Consumers can cancel a distance contract within 14 days of receiving the goods, without giving a reason and without penalty (Art. 9).
- **14-day refund window.** After the trader is informed of withdrawal, they must refund *all* payments received — including original shipping — within 14 days, using the original payment method (Art. 13).
- **Return shipping.** The consumer generally pays return shipping *only if* the trader clearly informed them of this before purchase. If the trader failed to disclose this, the trader bears the return cost (Art. 14).
- **Pre-contract information.** Before purchase, the trader must clearly provide: identity, geographic address, phone, email, total price, delivery arrangements, withdrawal conditions, and the legal guarantee of conformity (Art. 6). The burden of proving compliance is on the trader.
- **Non-conforming goods.** Under the related Sale of Goods Directive (2019/771/EU), if delivered goods don't match the description, the consumer is entitled to repair, replacement, price reduction, or full refund — and the trader bears the cost of returning non-conforming goods.

### Unfair Commercial Practices Directive (2005/29/EC)

Prohibits misleading business-to-consumer practices. Relevant violations by dropshipping scams:

- **Misleading actions (Art. 6).** False or deceptive information about a product's main characteristics, composition, or "results to be expected from its use" — e.g. polyester described as leather, or product photos that don't match what ships.
- **Misleading omissions (Art. 7).** Hiding or obscuring material information the consumer needs to make an informed decision, including the true origin of goods and actual shipping times.
- **Bait advertising (Annex I).** Offering products the trader has no reasonable grounds to supply at the advertised specification or price.
- **Bait-and-switch (Annex I).** Advertising one product and delivering something materially different.
- **Fake reviews (Annex I).** Submitting or commissioning fake consumer reviews, or falsely claiming reviews come from actual purchasers.

### Practical implications for a wronged buyer

- A demand that the buyer pay to ship a non-conforming product back to China is likely **unenforceable** under the Consumer Rights Directive if the trader didn't disclose this up front — and even then, non-conforming goods are returned at the trader's cost.
- The buyer can cite these directives in a chargeback dispute with their bank or card network; "goods not as described" is a standard chargeback reason code and the EU legal backing strengthens the claim.
- Buyers can report the trader to their national consumer protection authority (e.g. the European Consumer Centre Network, ECC-Net) which can pursue cross-border cases.

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

### Next Steps

[For buyers who have already ordered and have a complaint:]
- **Consumer protection authority** — name and link the local authority for the seller's actual jurisdiction (not the fake one in the store name). In the EEA, point to the European Consumer Centre Network (ECC-Net). In the US, the state attorney general and FTC. In Canada, the Competition Bureau / provincial consumer protection office.
- **Platform dispute** — link the platform's own guidance. For Shopify stores: https://help.shopify.com/en/manual/compliance/legal/dropshipping and https://www.shopify.com/legal/terms. Shopify requires merchants to publish an accurate refund policy and can terminate non-compliant stores.
- **Chargeback** — advise the buyer to file a chargeback with their credit card issuer or payment provider (PayPal dispute, card "goods not as described" reason code). Include the evidence from this analysis. This is usually the fastest path to a refund when the seller is overseas and uncooperative.
- **EU buyers** — cite the specific directives above (Consumer Rights Directive 2011/83/EU and Unfair Commercial Practices Directive 2005/29/EC) in correspondence and chargeback filings.
```

## Sources

Analysis methodology based on guidance from:
- BC Gov Information Security Branch — Drop Shipping Scams infosheet
- Chargeflow — How to Spot and Avoid Dropshipping Scams
- DoDropshipping — How to See if a Store is Dropshipping
- Michigan Consumer Protection — Before You Buy or Sell Online
- r/FrugalFemaleFashion — How to Tell if a Store is a Dropship Site
