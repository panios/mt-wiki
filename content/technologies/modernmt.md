---
type: technology
tags:
  - topic/translation
  - mt
  - adaptive
  - cloud-only
sources:
  - ModernMT _ Welcome
  - ModernMT _ Translators
  - Translated merges with ModernMT
  - Machine Translation in 2026_ An Honest Assessment of What's Good, What's Bad, and What's Next
last_updated: 2026-05-23
---

# ModernMT

Italian-origin adaptive MT engine, owned by [Translated](https://translated.com)
since the 2022 merger. Co-founded in 2017 by Translated, Fondazione
Bruno Kessler, the University of Edinburgh and TAUS as the
commercialization of an EU-funded research project; Translated
acquired all outside shares in May 2022 and folded ModernMT into its
product portfolio
([Translated press release](https://translated.com/modernmt-adaptive-machine-translation)).

The headline differentiators are **document-level translation**
(translating with full-document context rather than sentence-by-sentence)
and **human-in-the-loop real-time adaptation** (the model learns
from translator corrections in real time, with no retraining cycle)
([ModernMT](https://www.modernmt.com/)).

For per-engine market-context see [[../comparisons/mt-engines]].

## Product line

| Product | Hosting | Use case |
|---|---|---|
| ModernMT Cloud API | SaaS (Translated-hosted) | Enterprise integrations; API access via curl / Python / Java / Go / .NET / PHP / JavaScript ([ModernMT](https://www.modernmt.com/)) |
| ModernMT for Translators | SaaS via CAT-tool plugin | Translators using Matecat, SDL Trados, MemoQ ([ModernMT](https://www.modernmt.com/translators)) |
| Human-In-The-Loop product tier | SaaS | Premium tier where corrections continuously retrain the live model ([ModernMT](https://www.modernmt.com/)) |

ModernMT does **not** publicly offer an on-premise deployment option;
all integrations route through Translated's cloud
([ModernMT](https://www.modernmt.com/)).

## Technology

- **Architecture:** Patent-awarded neural MT with a "human-in-the-loop"
  training loop. Low-confidence translations are reviewed in the
  background by Translated's linguist network and feed back into the
  model
  ([ModernMT](https://www.modernmt.com/)).
- **Adaptation model:** Real-time learning from user corrections, with
  no retraining cycle. Document-level context handling is available
  at all service tiers; the real-time human-in-the-loop learning is
  gated to the premium tier
  ([ModernMT](https://www.modernmt.com/)).
- **Coverage:** 200 languages as of 2026
  ([ModernMT](https://www.modernmt.com/)). At the 2022
  merger ModernMT supported 56 languages, with 9 added immediately
  post-merger including Hindi and Xhosa
  ([Translated press release](https://translated.com/modernmt-adaptive-machine-translation));
  growth from 56 → 200 over four years suggests Translated has been
  actively investing in low-resource coverage.
- **Adjacent products from Translated:** *Lara* is Translated's
  next-generation translation AI (separate product line, positioned
  alongside ModernMT for first-draft translation); *TranslationOS* is
  Translated's workflow / orchestration layer
  ([Translated 2026 assessment](https://translated.com/resources/machine-translation-2026-assessment)).
  The Translated 2026 assessment positions Lara, not ModernMT, as the
  current flagship — worth confirming whether ModernMT remains a
  primary product or is being repositioned.

## Procurement-relevant features

Integration:

- REST API with SDKs in 7 languages (curl, JavaScript, Python, Go,
  Java, .NET, PHP)
  ([ModernMT](https://www.modernmt.com/)).
- Native plugins for Matecat (Translated's own CAT tool), SDL Trados,
  and MemoQ; other CAT tools integrate via the public API
  ([ModernMT](https://www.modernmt.com/translators),
   [Translated press release](https://translated.com/modernmt-adaptive-machine-translation)).

Compliance / security:

- ISO 27001:2013 certified for data centers, employee processes, and
  office operations
  ([ModernMT](https://www.modernmt.com/)).
- Vendor commits: "we will never use your translations to train the
  baseline engine or other client's engines"
  ([ModernMT](https://www.modernmt.com/)).
- **No on-premise / air-gap option** — all traffic transits Translated's
  cloud. Sovereignty-constrained clients should treat ModernMT as
  out-of-scope unless the SaaS posture is acceptable.

Recognition:

- Named a Leader in *IDC MarketScape: Worldwide Machine Translation 2023*
  ([ModernMT](https://www.modernmt.com/)).
- Awarded Gartner Cool Vendor (2019) and named one of the top-3
  customized MT engines in Intento's 2021 *State of Machine Translation*
  report
  ([Translated press release](https://translated.com/modernmt-adaptive-machine-translation)).

## Reference customers

Disclosed: Airbnb (quoted in vendor marketing as having "embedded
ModernMT within a human-centered translation process")
([ModernMT](https://www.modernmt.com/)).

## Where it fits / doesn't (business advisory)

- **Fits:** Cloud-tolerant clients with sustained translation volume
  who want adaptive MT with real-time learning from corrections;
  clients already using Matecat / Trados / MemoQ as their CAT
  environment; multinational enterprises where document-level coherence
  matters more than per-segment accuracy. The IDC MarketScape framing
  ("large, multinational corporation looking for adaptable multi-domain
  support") matches this profile
  ([ModernMT](https://www.modernmt.com/)).
- **Doesn't fit:** Clients with on-prem, air-gap, or data-residency
  requirements — no on-prem offering exists. Clients deciding on the
  basis of the broadest language coverage (Google Cloud Translation
  Advanced covers more pairs at the long tail); clients who treat
  human-in-the-loop as orthogonal to MT and procure linguists
  separately (LILT bundles this differently).
- **Worth verifying with the vendor:** whether Lara is replacing
  ModernMT as Translated's flagship MT product, since the 2026
  Translated assessment foregrounds Lara
  ([Translated 2026 assessment](https://translated.com/resources/machine-translation-2026-assessment)).

## Source-quality caveat

Three of the four sources are Translated / ModernMT marketing — the
ModernMT homepage, the translator-targeted product page, and the
press release announcing the merger. Specific *factual* attributes
(200 language coverage, ISO 27001, CAT plugin support, API SDKs,
merger date) are independently verifiable. The 2026 Translated
"honest assessment" essay is also vendor-published; its useful claims
for this page are about Translated's *current product portfolio*
(naming Lara and TranslationOS), which is verifiable. Its broader
claims about MT quality and TTE benchmarks should be treated as
positioning, not industry consensus.

The Intento and Gartner accolades are quoted in vendor marketing;
worth confirming against the original reports before propagating.

## Open questions

- Is ModernMT still actively developed, or being superseded by Lara
  inside Translated's portfolio?
- Does Translated offer a dedicated tenancy or VPC option for clients
  with softer-than-on-prem residency requirements (e.g. EU-only
  hosting), or is it strictly multi-tenant SaaS?
- How does ModernMT's adaptive-learning approach compare to LILT's
  Contextual AI in production benchmarks?

## Sources

- [ModernMT _ Welcome](https://www.modernmt.com/) — ModernMT homepage; product positioning, certifications, customer quotes, IDC MarketScape badge.
- [ModernMT _ Translators](https://www.modernmt.com/translators) — ModernMT product page targeted at individual translators; CAT-tool integrations, pricing model hints.
- [Translated merges with ModernMT](https://translated.com/modernmt-adaptive-machine-translation) — Translated's 2022 press release announcing the merger; corporate history, founding consortium, language coverage at merger time.
- [Machine Translation in 2026_ An Honest Assessment of What's Good, What's Bad, and What's Next](https://translated.com/resources/machine-translation-2026-assessment) — Translated thought-leadership essay on enterprise MT in 2026; mentions Lara and TranslationOS alongside (not replacing) ModernMT.
