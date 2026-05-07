---
type: technology
tags:
  - topic/translation
  - mode/advise
  - mt
  - meta-platform
  - shopify
  - ecommerce
sources:
  - Transcy Translation Engines_ Which One Best Suits You_
last_updated: 2026-05-01
---

# Transcy

Shopify-focused **MT meta-platform** — sits between an e-commerce
merchant and 8 underlying translation engines (Google Translate,
DeepL, OpenAI, Baidu, Gemini, Yandex, Grok, DeepSeek), letting the
merchant pick per-translation which engine to use
([source](https://transcy.io/blog/translation-engine-guide/)).
Their pitch is "20K+ eCommerce brands."

For per-engine considerations see [[../comparisons/mt-engines]].

## Shape

- **Distribution channel:** Shopify App Store. Not a general-purpose
  MT API.
- **Customer:** e-commerce merchants translating storefront content
  (product pages, marketing copy, theme strings).
- **Architecture:** meta-platform / aggregator — Transcy itself is
  not an MT engine, it's a routing layer plus Shopify integration
  plus a UI for managing translation jobs across engines
  ([source](https://transcy.io/blog/translation-engine-guide/)).

## Access models

Two billing / integration patterns
([source](https://transcy.io/blog/translation-engine-guide/)):

| | BYOK ("Authentication key") | Pay-per-use |
|---|---|---|
| Plan tier | Premium and Enterprise | All paid plans |
| Cost | No Transcy markup; merchant pays engine vendor directly | $1 per 1000 words, billed by Transcy |
| Tone control | Yes (where the engine supports it) | No |
| Onboarding | Merchant must hold an account with the engine vendor | Zero engine-side onboarding |

## Procurement notes (`mode/advise`)

Where Transcy fits, and where it doesn't:

- **Fits:** Shopify merchant, low-to-mid translation volume,
  doesn't want to manage 8 separate vendor relationships.
- **Doesn't fit:** non-Shopify platforms; enterprise volume where
  $1/1000-words PPU dominates costs and BYOK plan-tier requirements
  push the merchant onto Transcy's higher tiers; data-sovereignty
  requirements that need on-prem MT (Transcy is SaaS — the engines
  it routes to are independently SaaS, except DeepL on-prem and
  self-hosted DeepSeek, but using those *through* Transcy still
  routes data through Transcy's SaaS).
- **Sovereign / sensitive content:** if the client requires
  on-prem or air-gap MT, Transcy is out — recommend going direct
  to a self-hostable engine (DeepL on-prem, DeepSeek weights,
  open-source NLLB/M2M100) instead of through a meta-platform.

## Source-quality caveat

The only source so far is Transcy's own marketing material. Anything
on this page about Transcy's *positioning* is by definition
self-reported. Independent reviews, customer references, and
performance/reliability data needed before recommending or
counter-recommending in a real procurement deliverable.

## Open questions

- Transcy's data-handling policy — does it retain customer
  translation content? Train on it? PII implications?
- What does Transcy's BYOK actually look like operationally — does
  customer content traverse Transcy's servers, or is the engine
  call client-side?
- How does Transcy compare to other Shopify translation apps
  (Weglot, Langify, Shopify's own native translation)?
- Independent customer reviews and churn signal.

## Sources

- [Transcy Translation Engines_ Which One Best Suits You_](https://transcy.io/blog/translation-engine-guide/) — Transcy blog, vendor self-marketing, captured 2026-05-01.
