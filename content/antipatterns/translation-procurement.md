---
type: antipattern
tags:
  - topic/translation
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
  - The 2026 Nimdzi 100
  - 2025 Language Technology Radar Report
  - 2024.wmt-1.1
  - 2025.wmt-1.22
last_updated: 2026-05-23
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

Sometimes acceptable for business-advisory clients with softer
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

### IKEA-ization: skipping human review on AI-only output

Buyers using raw AI / LLM output for content previously categorised
"not for MT" — to slash budgets and reduce vendor dependency. The
output looks fluent, the cost looks low, and the demo passes. In
production, AI hallucinations and culturally-loaded mistranslations
surface in high-stakes content; the buyer returns to the LSP for
"expert-in-the-loop validation" after the damage is done
([Nimdzi 100](https://www.nimdzi.com/nimdzi-100-2026)).

Nimdzi's 2026 industry summary names this explicitly: "the
*IKEA-ization* of localization, where buyers favor the speed of AI
output to reduce dependency and slash budgets" — and frames the
LSP's role as "defending the necessity of human oversight against
the liability risks of AI hallucinations"
([Nimdzi 100](https://www.nimdzi.com/nimdzi-100-2026)). The pattern
is well-documented enough across the industry to flag at
RFP-evaluation time: any RFP that prices on "100% AI output" with no
human-review budget for regulated/high-stakes content is making this
mistake.

In business-advisory engagements: explicitly model human-review cost
in the cost comparison, not just MT API spend. In IT-consultation /
infrastructure work: ensure the build includes a quality-routing
mechanism (QE → human review for low-confidence segments) rather
than naive direct-to-publish from MT.

### Procuring on automatic-metric leaderboards

Vendor pitches and analyst reports routinely anchor on
*automatic-metric* scores (COMET, BLEU, MetricX, CometKiwi) as the
ranking signal. The metrics are cheap, deterministic, and look
authoritative. They are also **systematically biased** — and the
bias *increases* as systems hill-climb on the specific metric used
for evaluation.

Two concrete cases from the WMT shared task:

- **WMT24** — Unbabel-Tower70B topped the automatic ranking on
  AutoRank (a blend of MetricX-23-XL and CometKiwi-DA-XL) but did
  not win human evaluation. Reason: Unbabel used COMET as its
  reward signal during Minimum-Bayes-Risk decoding, so the model
  hill-climbed on the same metric that ranks it
  ([WMT24](https://aclanthology.org/2024.wmt-1.1/)).
- **WMT25** — Shy-hunyuan-MT placed first in automatic ranking for
  15 of 16 evaluated language pairs, but human evaluation
  consistently ranked it lower than Gemini 2.5 Pro and other
  systems
  ([WMT25](https://aclanthology.org/2025.wmt-1.22/)).

The WMT25 paper states the procurement implication directly:

> "Automatic rankings did not always match human judgments:
> systems that topped automated metrics such as Shy-hunyuan-MT
> did not consistently win under human evaluation, pointing to
> persistent metric bias in MBR and reinforcing that **human
> evaluation should remain the final arbiter of translation
> quality**." ([WMT25](https://aclanthology.org/2025.wmt-1.22/))

For business-advisory engagements: a vendor leading on "COMET"
or "MetricX" should be asked **explicitly** what their model was
trained or fine-tuned on. A vendor that uses metric X as a reward
signal will beat competitors on metric X without necessarily
producing better translations. The correct procurement protocol
is:

1. Use automatic metrics to *select* a shortlist (5–10 systems).
2. Run a **human evaluation** of the shortlist on
   representative client content (~50–200 segments per domain,
   per the WMT methodology).
3. Treat human evaluation as authoritative for the final ranking.

For IT-consultation work: same principle when picking among
open-source / self-hosted engines. NLLB benchmarks well on COMET
for many pairs, but human eval can show large quality gaps —
especially on mainstream language pairs where commercial LLMs have
improved fastest 2023–2025. See [[../comparisons/mt-evaluation]]
for the full methodology arc.

### Vibe-coding tooling around translation workflows

Linguists or LSPs experimenting with AI-assisted coding to spin up
translation dashboards, transcription wrappers, or alignment tools —
without grounding in software-engineering fundamentals. The tools
*look* correct (because GenAI produces working-looking code) but
have hidden defects: improper data storage, missing input
validation, broken integration boundaries
([Nimdzi Radar 2025](https://www.nimdzi.com/language-technology-radar-report)).

Nimdzi names this **"vibe coding"** and explicitly cautions linguists
moving into langtech development:

> "AI can produce code that looks correct but is subtly flawed.
> Without proper debugging or testing, linguist-developers risk
> deploying tools that break silently. Moreover, sensitive linguistic
> data, client files, or user information may be improperly stored,
> leading to privacy concerns."
> ([Nimdzi Radar 2025](https://www.nimdzi.com/language-technology-radar-report))

For procurement: if an LSP pitches a proprietary "AI-powered" tool
built recently and not subjected to external code review, ask
**explicitly** about data-storage architecture, integration boundary
testing, and the development team's software-engineering background.
A custom-built langtech tool from a non-engineering shop is a real
audit risk — the LSP may not realise they're storing client TM data
unencrypted in a "vibe-coded" dashboard.

For IT-consultation: pair linguist-developers with engineers for
anything touching client data. Reuse battle-tested platforms
(Custom.MT, Intento, the established TMSes) rather than spinning up
bespoke tooling.

## How to use this page

For business-advisory engagements: walk a client RFP / vendor list
through this catalog before the shortlist is finalised. Each
architectural trap is a hard-fail filter; each procurement trap is a
process check.

For IT-consultation / infrastructure work: the architectural section
is the more relevant one.
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
- [The 2026 Nimdzi 100](https://www.nimdzi.com/nimdzi-100-2026) — Nimdzi 100; "IKEA-ization of localization" framing for AI-only-output procurement antipattern.
- [2025 Language Technology Radar Report](https://www.nimdzi.com/language-technology-radar-report) — Nimdzi Radar; "vibe coding" warning for linguist-built tooling around translation workflows.
- [2024.wmt-1.1](https://aclanthology.org/2024.wmt-1.1/) — WMT24 Findings (companion PDF); Unbabel-Tower70B case study for the "metric-bias from training-on-reward" failure mode.
- [2025.wmt-1.22](https://aclanthology.org/2025.wmt-1.22/) — WMT25 Findings (companion PDF); Shy-hunyuan-MT case study; explicit "human evaluation should remain the final arbiter" framing.
