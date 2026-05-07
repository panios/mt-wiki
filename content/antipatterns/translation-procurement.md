---
type: antipattern
tags:
  - topic/translation
  - mode/build
  - mode/advise
  - vendor-evaluation
  - on-prem
  - data-sovereignty
sources:
  - Transcy Translation Engines_ Which One Best Suits You_
  - Machine Translation with AI at scale_ Flexible, Private, Adaptive
  - Announcing The Forrester Wave™_ Translation Management Systems, Q3 2025, Our Inaugural Evaluation Of The Market
  - (11) Why You Should Choose an On-prem Translation System for Corporate Translation
  - Comparing Enterprise AI Translation Software in 2026_ Security, Deployment and Professional Accuracy, Comparing Enterprise AI Translation Software in 2026
  - 24 Top Translation Software (2025)
  - Best AI-Enabled Translation Services Reviews 2026
last_updated: 2026-05-07
---

# Translation procurement antipatterns

Catalog of antipatterns that have surfaced from sources ingested so
far. Each entry names the trap, why it bites, and where in the wiki
or in `raw/` it was identified. Useful as a checklist when reviewing
a vendor pitch or a client's draft RFP.

Two families, intermixed below:
- **Architectural** — deployments that look like they meet a
  constraint but don't (the trust-boundary leaks).
- **Procurement / research** — vendor-evaluation processes that
  produce confidently-wrong shortlists.

## Architectural antipatterns

### Hybrid MT with public-API fallback

On-prem (or self-hosted OSS) MT engine that **falls through to a
SaaS API** when it can't translate a segment — typically rare terms,
named entities, low-resource pairs.

The trust boundary leaks on **exactly the segments most likely to be
sensitive** (people's names, internal jargon, protected codes). Worse:
the leak is silent — the platform behaves as on-prem in normal traffic
and only egresses on the high-value cases. Identified in
[[../patterns/on-prem-translation]].

When reviewing an architecture: ask explicitly what happens on
out-of-vocabulary input. "It falls back to Google Translate for
unknowns" is a hard fail in any sovereignty-constrained deployment.

### "Private cloud" / VPC marketed as on-prem

Vendor-managed isolated tenancy positioned with on-prem-coded
language ("dedicated environment", "behind your perimeter"). It is
still SaaS — vendor staff have access, network egress is the
vendor's, the data is in the vendor's data center.

Sometimes acceptable for `mode/advise` clients with softer
sovereignty postures; **never acceptable** when the client says
"air-gap" or "no external network egress." Identified in
[[../patterns/on-prem-translation]] and visible in vendor pages —
e.g. SYSTRAN explicitly distinguishes its on-premises Server from a
"Private Cloud" deployment, framing them as different products with
different residency stories
([SYSTRAN](https://www.systransoft.com/translation-products/translate-server/)).

A milder form: Pangeanic's "Managed Private Cloud (ECO)" tier —
honestly named, but a buyer skim-reading "Pangeanic supports
on-prem" might pick the wrong tier
([Pangeanic](https://pangeanic.com/machine-translation)).

### SaaS routed through a meta-platform

Using a self-hostable engine (DeepL on-prem, DeepSeek weights,
NLLB) **through a SaaS aggregator** like Transcy. The engine itself
may be on-prem-capable, but the routing layer terminates on the
aggregator's SaaS — content traverses the aggregator's servers
regardless of the engine's deployment posture.

Identified in [[../technologies/transcy]] and
[[../patterns/on-prem-translation]]. Watch for it whenever a Shopify
app, a low-code workflow tool, or a "translation API hub" sits
between the customer and a sovereign-deploy engine.

### Speech / OCR pre-processing breaks the air-gap

A subtle variant: an on-prem MT engine paired with a SaaS speech
recogniser or SaaS OCR service to handle voice / scanned-document
inputs. The MT step is on-prem; the audio or document image went to
a public API first.

AppTek and SYSTRAN bundle speech and OCR into the same on-prem
product specifically to avoid this
([AppTek](https://www.apptek.ai/technology/machine-translation),
 [SYSTRAN](https://www.translationsoftware4u.com/systran-server-on-premise/)). When the MT
vendor doesn't, the customer is responsible for keeping the
preprocessing on-prem too.

## Procurement / research antipatterns

### Treating vendor-published rankings as findings

Redokun's "24 Top Translation Software (2025)" lists Redokun #1.
Transcy's "8 best translation engines" frames everything around
how it routes to those engines. ChapsVision publishes SYSTRAN and
concludes a 7-vendor comparison with "SYSTRAN is the most coherent
choice"
([Redokun](https://redokun.com/blog/translation-software),
 [Transcy](https://transcy.io/blog/translation-engine-guide/),
 [ChapsVision review](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/)).

The *factual scaffolding* of these sources (vendor lists,
certifications, deployment modes, prices) is often verifiable and
useful — the *rankings* and *recommendations* are positioning. Mix
the two and the shortlist is conflicted before the RFP ships.

Convention applied across the wiki: cite vendor-published comparisons
for structured attributes only; never propagate "best for X" claims
without independent confirmation. Source-quality caveats live on
each page.

### Cherry-picked statistics from vendor whitepapers

Lingvanex's on-prem pitch cites "~45% of breaches in cloud", "~60%
of IT leaders concerned about cloud", "70%+ cite workflow
customization", "57% of LSPs use in-house TMS", "80% of software
companies prioritize on-prem over SaaS"
([Lingvanex](https://www.linkedin.com/pulse/why-you-should-choose-on-prem-translation-system-corporate-5vksc/)).

The 80% Replicated figure in particular is sample-biased
(Replicated sells on-prem distribution tooling — its survey audience
self-selects). The *direction* of the trend (on-prem demand is
growing) matches the independent Mordor MT 12.36% edge/on-prem CAGR
through 2031
([Mordor MT](https://www.mordorintelligence.com/industry-reports/machine-translation-market)),
so the framing isn't wrong; the magnitudes are unsafe to quote.
Discussed at [[../patterns/on-prem-translation#On-prem advantages (vendor-cited)]].

Convention applied: use directions, not magnitudes, from
vendor-cherry-picked stats. If a percentage is load-bearing in a
deliverable, it needs an independent source.

### Treating a marketing source's factual errors as harmless

The MarketsandMarkets MT market source claimed "Google acquired
DeepL in 2022" — a verifiably false fact. Logged on
2026-05-01 and the source was retained for the segment taxonomy /
trend framing but **not used for citations**
([[../comparisons/translation-market-sizing#Source caveat]]).

A single false claim in a market-research document means the rest of
its specific numbers can't be relied on either. Generic framing
(taxonomy, trend direction) survives; specific dollar figures and
acquisitions don't.

### TMS lock-in via integration depth

Forrester's Q3 2025 TMS Wave reports a "substantial fraction" of
reference customers wanted to switch TMS providers but were held
back by the cost of their integration and customization
investment
([Forrester](https://www.forrester.com/blogs/announcing-the-first-forrester-wave-translation-management-systems-q3-2025/),
 [[../comparisons/translation-platforms]]).

The trap: pricing and feature comparisons during initial
procurement under-weight integration debt because it doesn't exist
yet. Two years later, 100+ connectors, custom workflows, vendor-
specific automation rules, and an internal team trained on the
TMS's quirks become a switching cost the org can't afford to pay.

Mitigations: contractually require export of TM, glossaries, and
workflow configurations in standard formats; cap the number of
*proprietary* integrations vs. integrations through neutral layers
(MCP, REST); track integration debt explicitly in vendor reviews.

### Treating a Gartner / analyst category as a shortlist

Gartner's "AI-Enabled Translation Services" category page lists 18
products in a single bucket — including pure TMSes, MT engines,
quality-estimation tools, customer-support translation, and a budget-
management product apparently miscategorised
([Gartner](https://www.gartner.com/reviews/market/ai-enabled-translation-services),
 [[../comparisons/translation-platforms]]).

Treating the category page as "the shortlist" mixes vendors whose
products aren't comparable — ModelFront (quality estimation) is
not an alternative to Smartling (TMS). Build the layer model
([[../comparisons/translation-platforms#Layer model]]) first, then
filter the analyst list against it.

### Conflating MT engine, TMS, and CAT tool

Same trap, smaller scope: marketing material routinely calls a TMS a
"translation tool" and an MT engine a "translation platform." A
modern TMS *includes* CAT capabilities and *integrates* MT engines —
the categories blur in vendor framing but procurement decisions are
different
([[../comparisons/translation-platforms#Layer model]]).

Decide which layer the client actually needs (translator-facing
editor / workflow orchestration / raw text-in-text-out) before
filtering vendors. A "we need an AI translation platform" RFP that
hasn't done this work will produce a shortlist mixing Trados,
Smartling, and DeepL — none of which are substitutes for the others.

### Procuring on raw quality scores when deployment is the threshold

ChapsVision's framing — "translation quality is now broadly
comparable across all seven solutions; deployment architecture and
compliance certifications are the real differentiators"
([ChapsVision review](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/))
— is the cleanest articulation of why **deployment / certifications
should be the *first* filter**, not the last.

Procurement that ranks vendors by BLEU / human-eval first and only
then asks "is it deployable?" can produce a #1 ranking that fails
the threshold criterion in step 2. The ChapsVision source is itself
conflicted, but the structural argument matches the regulatory
drivers in [[../patterns/on-prem-translation]]. Filter on
deployment + compliance first; rank on quality within the survivors.

### "Solo operator buys enterprise infrastructure"

Build-mode-specific. A solo or two-person team selects an on-prem
TMS or MT stack with the right *features* but **operational shape
that needs a team to babysit** (Kubernetes operator, model-update
pipeline, dedicated GPU host, monitoring stack, certificate rotation).

Flagged in `context.md` as a hard constraint for Build mode and in
[[../patterns/on-prem-translation#When SaaS dominates instead]].
Symptoms: model gets stale because nobody owns the refresh, monitoring
goes unread, the on-prem deployment turns into a worse version of the
SaaS it replaced. For solo operators the right shape is OSS engines
that ship as a single binary or container with manual model updates,
or vendor on-prem products with clear offline update bundles — not
distributed-systems-shaped enterprise stacks.

## How to use this page

In `mode/advise`: walk a client RFP / vendor list through this
catalog before the shortlist is finalised. Each architectural trap
is a hard-fail filter; each procurement trap is a process check.

In `mode/build`: the architectural section is the more relevant one.
"Solo operator buys enterprise infrastructure" is the failure mode
that bites Build mode hardest.

## Sources

- [Transcy Translation Engines_ Which One Best Suits You_](https://transcy.io/blog/translation-engine-guide/) — Transcy blog; example of vendor-published rankings positioned as a guide.
- [Machine Translation with AI at scale_ Flexible, Private, Adaptive](https://pangeanic.com/machine-translation) — Pangeanic; honest naming of "Managed Private Cloud" tier vs. on-prem.
- [Announcing The Forrester Wave™_ Translation Management Systems, Q3 2025, Our Inaugural Evaluation Of The Market](https://www.forrester.com/blogs/announcing-the-first-forrester-wave-translation-management-systems-q3-2025/) — Forrester Wave teaser; TMS lock-in finding.
- [(11) Why You Should Choose an On-prem Translation System for Corporate Translation](https://www.linkedin.com/pulse/why-you-should-choose-on-prem-translation-system-corporate-5vksc/) — Lingvanex; example of cherry-picked vendor whitepaper statistics.
- [Comparing Enterprise AI Translation Software in 2026_ Security, Deployment and Professional Accuracy, Comparing Enterprise AI Translation Software in 2026](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/) — ChapsVision review; threshold-criterion framing and self-conflicted recommendation.
- [24 Top Translation Software (2025)](https://redokun.com/blog/translation-software) — Redokun; vendor self-#1-ranking example.
- [Best AI-Enabled Translation Services Reviews 2026](https://www.gartner.com/reviews/market/ai-enabled-translation-services) — Gartner category page; conflated-categories example.
