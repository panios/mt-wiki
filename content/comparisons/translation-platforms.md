---
type: comparison
tags:
  - topic/translation
  - mode/advise
  - vendor-evaluation
  - tms
  - localization
sources:
  - Announcing The Forrester Wave™_ Translation Management Systems, Q3 2025, Our Inaugural Evaluation Of The Market
  - Best AI-Enabled Translation Services Reviews 2026
  - 24 Top Translation Software (2025)
  - Comparing Enterprise AI Translation Software in 2026_ Security, Deployment and Professional Accuracy, Comparing Enterprise AI Translation Software in 2026
  - Enterprise AI Translation Platform
last_updated: 2026-05-07
---

# Translation platforms (TMS / CAT / AI translation services)

Procurement-oriented vendor catalog for translation **platforms** —
the orchestration / workflow / CAT / TMS layer that sits *above* MT
engines. For the engines themselves see [[mt-engines]]. For market
sizing and segment shares see [[translation-market-sizing]].

## Layer model

Three distinct vendor categories get conflated in marketing material;
the sources below each focus on a different one.

| Layer | What it does | Examples | Source coverage |
|---|---|---|---|
| MT engine | Raw text-in / text-out translation | Google Translate, DeepL, Amazon Translate, NLLB | [[mt-engines]] |
| TMS / localization platform | Workflow orchestration, project mgmt, integrations, vendor & cost mgmt, AI agents | Phrase, Smartling, Lokalise, RWS, memoQ | Forrester Wave |
| CAT tool | Translator-facing editor: TM, glossaries, segment view | SDL Trados, memoQ translator pro, OmegaT, Wordfast | Redokun |
| AI translation service (Gartner category) | Bundled GenAI-augmented translation, sometimes overlapping TMS | Crowdin, Lokalise, Phrase, Lilt | Gartner |

A modern TMS often *includes* CAT capabilities and *integrates* MT
engines — the categories blur. Forrester's framing
([source](https://www.forrester.com/blogs/announcing-the-first-forrester-wave-translation-management-systems-q3-2025/))
calls modern TMSes "vendor-neutral orchestration layers that unify
fragmented technologies and functions" — meaning the TMS is the layer
that selects and routes among engines and humans, not a translator
itself.

## Forrester Wave Q3 2025 cohort

The 12 vendors Forrester evaluated in its inaugural TMS Wave
([source](https://www.forrester.com/blogs/announcing-the-first-forrester-wave-translation-management-systems-q3-2025/)).
The teaser blog does not publish the rankings — only the cohort.

| Vendor | Notes |
|---|---|
| Bureau Works | — |
| Centific | — |
| LILT | Hybrid neural + curated human post-editing networks for regulated industries ([Mordor MT](https://www.mordorintelligence.com/industry-reports/machine-translation-market)) |
| Lionbridge | Aurora AI content orchestration engine, July 2024 ([Mordor TSM](https://www.mordorintelligence.com/industry-reports/translation-services-market)) |
| Lokalise | Dev-tool-integrated (GitHub, Figma, Adobe, Contentful); also appears on Redokun and Gartner lists |
| memoQ | Also widely used as desktop CAT; memoQ translator pro is Windows-only |
| Phrase | "Language Intelligence Platform"; ISO 27001 certified; expanded alliance with Welocalize Oct 2024 ([Mordor TSM](https://www.mordorintelligence.com/industry-reports/translation-services-market)) |
| RWS | Absorbed SDL; Language Weaver MT is default for 55% of first-pass content ([Mordor TSM](https://www.mordorintelligence.com/industry-reports/translation-services-market)) |
| Smartling | Workflow customization, integration-heavy |
| TransPerfect | Surpassed USD 1.2B revenue in 2023 with GlobalLink platform; acquired Unbabel just before Wave publication ([Mordor TSM](https://www.mordorintelligence.com/industry-reports/translation-services-market), [Forrester](https://www.forrester.com/blogs/announcing-the-first-forrester-wave-translation-management-systems-q3-2025/)) |
| Unbabel | Now part of TransPerfect (post-Wave-publication); was hybrid AI + human ([Mordor MT](https://www.mordorintelligence.com/industry-reports/machine-translation-market)) |
| XTM | XTM Cloud TMS; visual-context editor |

A "substantial fraction" of reference customers told Forrester they
*wanted* to switch TMS providers but were held back by the cost of
their integration and customization investment — TMS lock-in is real
and worth flagging as a procurement risk
([source](https://www.forrester.com/blogs/announcing-the-first-forrester-wave-translation-management-systems-q3-2025/)).

## Gartner AI-Enabled Translation Services cohort

Gartner's category covers a wider spread — bundling pure-play TMSes
with embedded-AI translation services
([source](https://www.gartner.com/reviews/market/ai-enabled-translation-services)).
18 products listed; only the more substantively described ones below.
"Be the first to" entries on Gartner have no review data yet.

| Product | Vendor | Distinct positioning |
|---|---|---|
| Crowdin | Crowdin | 600+ tool integrations; apps/software/websites/games/docs |
| Lokalise | Lokalise | Dev-tool integrated (GitHub, Figma, Adobe, Contentful); Translation Scoring for QA |
| Phrase | Phrase | Single-environment TMS+software-localization+multimedia+MT+language AI; ISO 27001 |
| Smartling | Smartling | Workflow-driven, integration-heavy |
| Pairaphrase | Pairaphrase | 140+ languages, 20K+ pairs, 25+ file types incl. PDFs/InDesign; "AI Sandbox" for transcreation and proprietary-model training |
| Unbabel | Unbabel (now TransPerfect) | AI + human for customer-support translation; ticket/chat focus |
| Language I/O | Language I/O | Real-time CX support translation embedded in support platforms |
| ModelFront | ModelFront | Quality estimation only — checks/fixes AI translations and triggers human review; "no engineering, no workflow change, no external models, only private custom LLMs" |
| GlobalLink AI | TransPerfect | TMS + workflow automation with AI agents |
| Language Cloud TMS | (RWS) | RWS's TMS offering |
| Lilt | Lilt | AI + human expertise hybrid |
| MachineTranslation.com | MachineTranslation.com | Engine *evaluation* tool — compares MT engines on fluency/adequacy/terminology |
| ModelFront | ModelFront | (see above) |
| Neural MT Platform | AppTek | Neural MT for text + audio; real-time; API-integrable |
| TranslationOS | Translated | TMS with project mgmt, vendor coordination, translation memory, terminology, analytics |
| XTM Cloud | XTM | TMS, also in Forrester cohort |
| YeeKit | GTCOM | Chinese vendor; MT, cross-lingual semantic understanding, NLP |
| CleverSo | CleverSo | CAT-style: TM, terminology, collaborative translation |

Note: Gartner's listing for "Centus" describes it as a budget-management
tool, not translation software — the listing appears to be miscategorized
or describe a different Centus product
([source](https://www.gartner.com/reviews/market/ai-enabled-translation-services)).

## Redokun's CAT/TMS catalog

Redokun's list ([source](https://redokun.com/blog/translation-software))
is the most pricing-transparent of the three sources. It blends modern
SaaS TMSes with desktop CAT tools and freelance-translator software —
useful when the "platform" question is really about a freelance or
small-team workflow rather than enterprise localization.

Pricing is the standout signal here. The sources above mostly hide
pricing behind "contact sales."

### SaaS TMS / localization platforms

| Product | Type | Cloud/Desktop | Starts at | Notable |
|---|---|---|---|---|
| Redokun | TMS, CAT | Cloud | $125/mo | InDesign-focused historically, expanded to Office/other |
| Smartcat | TMS, CAT | Cloud | $249/mo (freemium tier exists) | Vendor marketplace, automatic billing |
| Lokalise | TMS, CAT | Cloud | $90/mo | App localization, design-tool plugins higher tier only |
| Text United | TMS, CAT | Cloud | $71/mo | ASR-based audio/video translation |
| Transifex | TMS, CAT | Cloud | $70/mo | Edit Lock, community translation voting |
| LingoHub | TMS, CAT | Cloud | $29/mo | App/game/website focus, GitHub/GitLab/Bitbucket sync |
| Smartling | TMS, CAT | Cloud | $200/mo | Steep learning curve |
| Phrase | Software localization | Cloud | $23/user/mo | Branching/versioning, large platform |
| Crowdin | Localization mgmt | Cloud | $40/mo | Free with conditions (translations donated to Crowdin TM) |
| Weglot | Website localization | Cloud | $23/mo | CMS-plugin-based, multilingual SEO |
| POEditor | Localization | Cloud | $14.99/mo | Crowdsourced translation option |
| Pairaphrase | TMS, CAT | Cloud | $2,199/yr | Voiceover translation |
| GlobalLink | TMS | Cloud | Not public | Enterprise; mobile/web/gaming localization |
| XTM Cloud | TMS, CAT | Cloud | $61/mo | Visual editor for in-context translation |
| Cloudwords | TMS, CAT | Cloud | Not public | Marketing-content focus |

### Desktop CAT tools

| Product | Cloud/Desktop | Pricing | Notable |
|---|---|---|---|
| SDL Trados Studio | Desktop (cloud add-on) | ~$2,933 license | Industry default for translation agencies; relatively expensive, support/maintenance separate |
| memoQ translator pro | Desktop (cloud add-on) | $770 individual | Windows-only; full features need memoQ server |
| OmegaT | Desktop | Free, open-source | Windows/Mac/Linux; freelancer-targeted |
| CafeTran Espresso | Desktop | ~$95/yr | Windows/Mac/Linux; built by translator |
| Wordfast Pro | Desktop | $460/license | Windows/Mac/Linux; claims SDL Trados package import (compatibility caveats per reviewers) |
| Swordfish Translation Editor | Desktop | $120/yr | Open-source-ish (free for personal); cross-OS; integrates DeepL/Azure/Google/MyMemory/Yandex MT |
| Transit NXT Professional+ | Desktop | Not public | Non-sentence-based TM (full context); steep learning curve |
| MetaTexis for Word | Desktop | $45/license | Runs inside Microsoft Word; Trados-package import in some licenses |
| Matecat | Cloud (free) | Free | Open-source; lag and privacy concerns reported |

The freelancer/small-team CAT segment is where price compression and
OSS viability are most visible — OmegaT (free) and CafeTran ($95/yr)
viable alternatives to SDL Trados ($2,933) for individual translators
([source](https://redokun.com/blog/translation-software)).

### Caveats on the Redokun list

- Redokun is itself listed as #1 — vendor-published comparison, treat
  positioning of #1 with skepticism.
- Pricing tiers reflect entry plans; enterprise / volume tiers will be
  materially different.
- The list is dated "2025" but blends entries from earlier years
  (Smartling pricing language reads like 2022); double-check pricing
  before any procurement deliverable.

## Deployment / data-residency annotations

This is the dimension that matters most for `mode/advise` clients
with sovereignty constraints. **None of the three sources specify
deployment posture per platform** — these annotations are inferred
from each vendor's public posture and need verification per
engagement.

| Platform | Likely deployment | Likely residency story |
|---|---|---|
| Phrase | SaaS | EU + US regions; ISO 27001 |
| Smartling | SaaS | US-led |
| Lokalise | SaaS | EU-headquartered |
| RWS / Language Cloud | SaaS + private deployment options | EU + US; regulated-industry capable |
| TransPerfect / GlobalLink | SaaS + on-prem options | Global, regulated-industry capable |
| Lionbridge | SaaS | Global |
| memoQ | Desktop + memoQ Server (self-host) | Self-hostable |
| SDL Trados Studio | Desktop | Local-only by default; cloud add-on optional |
| OmegaT | Desktop, OSS | Local-only |
| Crowdin | SaaS | EU/US |
| Pairaphrase | SaaS + "AI Sandbox" private models | US-led; private-model option exists |
| ModelFront | SaaS, "private custom LLMs" | Vendor claims privacy; verify |

For sovereignty-constrained clients, the short list narrows to:
**self-hostable CAT tools** (memoQ Server, OmegaT, SDL Trados Studio
local-only) and **TMSes with on-prem options** (RWS,
TransPerfect/GlobalLink). Most modern SaaS-only TMSes (Phrase,
Smartling, Lokalise, Lilt) are out of scope unless the client accepts
their regional cloud arrangements.

## Certifications cohort spotlight (from ChapsVision 2026 review)

The ChapsVision enterprise-MT review
([source](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/))
provides the most concrete published certification comparison in the
sources captured so far. While its scope is the engine layer (see
[[mt-engines]]), the certification shapes are directly relevant to
TMS / platform vendors that bundle those engines.

| Certification | Relevant in cohort | Note |
|---|---|---|
| GDPR | All seven (SYSTRAN, RWS, LILT, DeepL, MS, AWS, GCP) | Table-stakes for EU clients ([ChapsVision review](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/)) |
| ISO 27001 | SYSTRAN, RWS, DeepL, LILT (via ISO 17100/18587 + others) | Also held by Phrase per [[#Forrester Wave Q3 2025 cohort]] |
| SOC 2 Type II | DeepL, LILT, MS Azure, AWS, GCP | LILT explicitly holds Type II |
| HIPAA | DeepL, LILT, MS Azure, AWS, GCP | Plus SYSTRAN-via-on-prem-deployment (data never leaves perimeter) |
| FedRAMP / DoD | AWS (FedRAMP High + GovCloud), MS Azure Government | Threshold for US federal procurement |
| FDA CFR Part 11 | **LILT only** | Pharmaceutical clinical-trial threshold ([ChapsVision review](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/)) |
| ISO 9001 / 17100 / 18587 | LILT | Translation-services / post-editing quality standards |
| Cyber Essentials | LILT | UK government baseline |

LILT carries the broadest stack in the cohort
([ChapsVision review](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/),
 [LILT](https://lilt.com/)). For
clients procuring **a platform** rather than just an engine, that
combination matters: LILT positions itself as a TMS-equivalent
agentic-AI platform that orchestrates workflows end-to-end
([LILT](https://lilt.com/)),
overlapping with the Forrester Wave / Gartner cohorts above.

## Open questions

- Forrester Wave **scoring** — the teaser blog publishes only the
  cohort; the full Wave (paywalled) gives leader/strong-performer/
  contender placement and per-criterion scores. Required for any
  vendor-shortlist deliverable.
- **TMS pricing transparency** — most enterprise TMSes hide pricing.
  Need vendor RFPs or analyst data (Nimdzi, CSA Research, Slator) for
  comparable cost figures.
- **Lock-in / switching cost** quantification — Forrester noted a
  "substantial fraction" of customers wanted to switch but were stuck.
  Procurement should treat integration depth as a long-tail cost.
- **Domain-specific suitability** — none of these sources segment by
  domain (legal, medical, financial). For a regulated-domain client
  this is the load-bearing question.
- **AI-agent capabilities** are not standardized across TMSes per
  Forrester. Need per-vendor demo/POC to evaluate.

## Sources

- [Announcing The Forrester Wave™_ Translation Management Systems, Q3 2025, Our Inaugural Evaluation Of The Market](https://www.forrester.com/blogs/announcing-the-first-forrester-wave-translation-management-systems-q3-2025/) — Forrester teaser for paywalled Wave; vendor cohort + market framing.
- [Best AI-Enabled Translation Services Reviews 2026](https://www.gartner.com/reviews/market/ai-enabled-translation-services) — Gartner AI-enabled translation services category page; 18 product listings.
- [24 Top Translation Software (2025)](https://redokun.com/blog/translation-software) — Redokun blog; pricing-transparent CAT/TMS catalog, vendor-published (Redokun is listed first).
- [Comparing Enterprise AI Translation Software in 2026_ Security, Deployment and Professional Accuracy, Comparing Enterprise AI Translation Software in 2026](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/) — ChapsVision review; certification cohort comparison across the 7 most-evaluated enterprise MT vendors.
- [Enterprise AI Translation Platform](https://lilt.com/) — LILT homepage; agentic-AI platform positioning, 100+ connector ecosystem, BYO-model option.
