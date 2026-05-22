---
type: comparison
tags:
  - topic/translation
  - mt
  - market-sizing
sources:
  - Machine Translation Market - Size, Companies & Share
  - Translation Service Market Size, Drivers & Opportunities
  - Announcing The Forrester Wave™_ Translation Management Systems, Q3 2025, Our Inaugural Evaluation Of The Market
  - Machine Translation Market Outlook, Size, Share, Trends, Growth Drivers, Key Players, and Regional Insights
  - The 2026 Nimdzi 100
  - 2025 Language Technology Radar Report
  - Intento Releases 9th Annual “State of Translation Automation 2025” Industry Report
last_updated: 2026-05-23
---

# Translation market sizing

Reference page for business-advisory deliverables that need market-size,
growth-rate, segment-mix, or regional-share figures. Three distinct
markets get conflated routinely; pin the scope before quoting numbers.

## Three markets, not one

These are different scopes. Quoting an "MT market" number when the
client actually means "translation services" overstates / understates
by ~50x.

| Market | What it covers | 2026 size | 2031 forecast | CAGR |
|---|---|---|---|---|
| Machine translation (MT) | Software/API spend on automated translation engines | USD 1.26B ([Mordor MT](https://www.mordorintelligence.com/industry-reports/machine-translation-market)) | USD 2.19B | 11.69% |
| Translation services | Full LSP market: human + machine + interpretation + transcreation | USD 64.99B ([Mordor TSM](https://www.mordorintelligence.com/industry-reports/translation-services-market)) | USD 97.65B | 8.44% |
| TMS (translation management systems) | Enterprise platforms orchestrating localization workflows; not separately sized in sources here | — | — | — |

The MT market is ~2% of the translation services market by revenue,
but software's share of services revenue is 72.88% in 2025
([Mordor TSM](https://www.mordorintelligence.com/industry-reports/translation-services-market))
— meaning a lot of "services" billings are actually services-wrapping-
software-output, not pure human work.

Forrester's TMS Wave evaluated 12 vendors (Bureau Works, Centific,
LILT, Lionbridge, Lokalise, memoQ, Phrase, RWS, Smartling,
TransPerfect, Unbabel, XTM) and was published Q3 2025 — Forrester's
inaugural evaluation, suggesting the TMS category is only now
considered worth a Wave
([Forrester](https://www.forrester.com/blogs/announcing-the-first-forrester-wave-translation-management-systems-q3-2025/)).

## MT market — segment mix

By technology (2025 share)
([Mordor MT](https://www.mordorintelligence.com/industry-reports/machine-translation-market)):

- Neural MT — 56.73%, growing at 12.71% CAGR (transformer-led)
- Rule-based and statistical — residual, surviving only in regulated
  niches like defense where deterministic output is mandated
- Hybrid (NMT + terminology databases) — used by automotive and
  life-science publishers; lowers post-editing effort by ~30%

By deployment (2025 share)
([Mordor MT](https://www.mordorintelligence.com/industry-reports/machine-translation-market)):

- Cloud — 71.24%, but growing slower than edge
- Edge / on-device — projected 12.36% CAGR through 2031, the fastest
  among deployment modes; driven by automotive (offline voice
  translation), DoD air-gap mandates, HIPAA-driven healthcare local
  inference

This edge/on-prem trend is the single most relevant market signal for
Build mode and for sovereignty-constrained Advise engagements — see
[[../patterns/on-prem-translation]].

By vertical (2025 share)
([Mordor MT](https://www.mordorintelligence.com/industry-reports/machine-translation-market)):

- BFSI — 21.36% (regulated multilingual disclosures, cross-border
  reporting)
- Healthcare and life sciences — fastest-growing at 13.66% CAGR;
  pharma sponsors report up to 50% reduction in clinical-trial
  localization costs

By application
([Mordor MT](https://www.mordorintelligence.com/industry-reports/machine-translation-market)):

- Static documents — 28.91% of 2025 revenue (largest)
- Live speech translation — fastest at 12.93% CAGR; video conferencing
  reports up to 60% increase in non-English-speaker participation when
  in-meeting translation enabled

## Translation services market — segment mix

By component (2025)
([Mordor TSM](https://www.mordorintelligence.com/industry-reports/translation-services-market)):

- Software — 72.88%, growing fastest at 10.34% CAGR (cloud-native)
- Hardware — declining, retained for on-prem conference interpretation
  and secure healthcare kiosks

By operation (2025)
([Mordor TSM](https://www.mordorintelligence.com/industry-reports/translation-services-market)):

- Machine + neural MT — 61.25%
- NMT with post-editing (hybrid) — 10.76% CAGR; the dominant
  enterprise pattern, accepting "80% machine quality at 80% lower cost
  arriving 10× faster"
- Pure human first-pass — still required in pharmaceuticals and
  litigation for liability reasons

By service (2025)
([Mordor TSM](https://www.mordorintelligence.com/industry-reports/translation-services-market)):

- Written translation — 53.62% (largest)
- Transcreation + multimedia localization — fastest at 12.79% CAGR;
  dubbing/subtitling/voice-over priced 40-60% above text work

By end-user (2025)
([Mordor TSM](https://www.mordorintelligence.com/industry-reports/translation-services-market)):

- IT and telecom — 32.55% (largest)
- Media and gaming — fastest at 12.43% CAGR; streaming back-catalog
  localization and Southeast Asian mobile-gaming USD 40B addressable
  market

## Geography

| Region | MT 2025 share | TSM 2025 share | Fastest-growing? |
|---|---|---|---|
| North America | 37.89% (largest) | — | — |
| Europe | — | 44.12% (largest, GDPR-driven) | — |
| Asia-Pacific | — | — | Both: MT 12.78% CAGR, TSM 15.02% CAGR |

Sources
([Mordor MT](https://www.mordorintelligence.com/industry-reports/machine-translation-market),
[Mordor TSM](https://www.mordorintelligence.com/industry-reports/translation-services-market)).

The MT market is North-America-led; the broader services market is
Europe-led — driven by GDPR multilingual documentation across 24
official EU languages and Brexit-overlap legal-translation premium
pricing
([Mordor TSM](https://www.mordorintelligence.com/industry-reports/translation-services-market)).

## Drivers

Cross-cutting drivers cited by both Mordor reports and Forrester:

- **Continuous localization in DevOps** — apps that practise it see
  128% download jumps and 26% revenue gains; release cycles compress
  from months to weeks
  ([Mordor TSM](https://www.mordorintelligence.com/industry-reports/translation-services-market)).
- **E-commerce localization** — 76% of shoppers decline non-localized
  purchases; multilingual storefronts achieve up to 50% higher AOV;
  cross-border online sales surpassed USD 1.2T in 2025
  ([Mordor TSM](https://www.mordorintelligence.com/industry-reports/translation-services-market),
  [Mordor MT](https://www.mordorintelligence.com/industry-reports/machine-translation-market)).
- **Regulatory language-access mandates** — Section 1557 of the ACA
  obliges US health systems to provide qualified interpreters in the
  15 most-spoken local languages from July 2025; federal agencies
  must translate vital documents into the top 12 non-English
  languages; EU regulations mandate digital-services content in all
  official languages
  ([Mordor TSM](https://www.mordorintelligence.com/industry-reports/translation-services-market)).
- **AI reshapes workflow, not just translation** — Forrester's
  framing: real uplift comes from workflow automation and AI agents,
  not raw MT improvements; TMS providers are not standardized in this
  respect
  ([Forrester](https://www.forrester.com/blogs/announcing-the-first-forrester-wave-translation-management-systems-q3-2025/)).

## Restraints

- **Sovereign data-privacy regulations** — GDPR raises operating
  expenses up to 20% via regional data-center routing and ISO 27001
  controls; HIPAA stacks more cost in US healthcare; enterprises with
  sensitive legal/financial content increasingly insist on
  on-premises or private-cloud workflows
  ([Mordor TSM](https://www.mordorintelligence.com/industry-reports/translation-services-market)).
- **Free / open-source MT commoditizing pricing** — OpenNMT, Marian,
  and Meta's NLLB enable self-hosted production engines with no
  licensing fees; companies with ML talent report 70-80% cost savings
  vs paid APIs in high-volume settings
  ([Mordor MT](https://www.mordorintelligence.com/industry-reports/machine-translation-market)).
- **Persistent low-resource accuracy gaps** — neural models still
  post error rates above 30% for many African and indigenous
  languages; Meta's NLLB yields BLEU below 20 for numerous pairs
  ([Mordor MT](https://www.mordorintelligence.com/industry-reports/machine-translation-market)).
- **Specialist linguist shortage** — technical/legal/medical content
  needs subject-expert linguists who command premium pay; remote work
  widened pool but intensified wage competition
  ([Mordor TSM](https://www.mordorintelligence.com/industry-reports/translation-services-market)).

## Competitive structure

- **MT market** — moderately concentrated; top 5 hold ~60-65%; Google,
  Microsoft, AWS bundle translation into broader cloud suites and
  compress per-character pricing; DeepL holds quality-led EU niche;
  Meta's NLLB (open-source, 200 languages) intensifies price
  pressure; specialists like RWS and SYSTRAN fortify positions in
  life sciences and legal via proprietary terminology databases
  ([Mordor MT](https://www.mordorintelligence.com/industry-reports/machine-translation-market)).
- **Translation services market** — fragmented; top 100 vendors hold
  only 15% of global billings; Teleperformance bought LanguageLine
  Solutions for USD 1.5B; private-equity roll-ups underway; white
  space in hybrid human-AI offerings, API-first localization toolkits,
  domain-specific engine fine-tuning
  ([Mordor TSM](https://www.mordorintelligence.com/industry-reports/translation-services-market)).

## Recent moves (Q4 2025 – Q1 2026)

From [Mordor MT](https://www.mordorintelligence.com/industry-reports/machine-translation-market):

- January 2026 — Google integrated Gemini into Google Translate for
  context-aware translation across 133 languages.
- December 2025 — Microsoft committed USD 150M to add 25 African and
  indigenous languages to Azure Translator by mid-2026.
- November 2025 — DeepL raised USD 300M Series C to expand into
  Asia-Pacific.
- October 2025 — AWS launched Amazon Translate Custom Terminology
  (enforced glossaries cut post-editing by up to 40%).

Forrester noted TransPerfect's acquisition of Unbabel just before
publication of the Wave; both vendors were evaluated separately
([Forrester](https://www.forrester.com/blogs/announcing-the-first-forrester-wave-translation-management-systems-q3-2025/)).

## Nimdzi 100 — broader language industry sizing

Nimdzi's 2026 industry report
([Nimdzi 100](https://www.nimdzi.com/nimdzi-100-2026)) sizes the
**entire language industry** (translation services + interpretation +
language-tech platforms + data services) at a wider scope than the
Mordor reports above. Useful as a cross-check on services-market
figures and as the reference for narrative-level Advise-mode claims.

| Metric | 2025 | 2026F | 2030F |
|---|---|---|---|
| Industry size (realistic) | USD 72.6B | USD 73.4B | USD 76.1B |
| Industry size (optimistic) | — | — | USD 96.9B (alt scenario) / USD 86.2B (alt) |
| CAGR (2025→2030, realistic) | — | — | < 1.0% |
| Top-100 share of industry | 19.8% | — | — |
| Top-10 share of industry | 9.9% | — | — |

Sources
([Nimdzi 100](https://www.nimdzi.com/nimdzi-100-2026)).

The Nimdzi figure (USD 72.6B in 2025) is **higher than Mordor's
translation-services figure** (USD 64.99B in 2026) — the gap is the
scope difference (Nimdzi includes interpreting, language-tech
licensing, data services; Mordor's services figure is more narrowly
translation-and-related services). Don't average across the two
numbers — pin scope first, then pick the right reference.

### Nimdzi observations affecting market trajectory

- **Linear, not exponential.** Nimdzi's 2026 outlook revised
  *downward* yet again — projected CAGR through 2030 is now < 1.0%.
  This conflicts with Mordor's 8.44% services CAGR and the 11.69% MT
  CAGR. The reconciliation: Mordor sizes the *software-driven*
  segments (which are growing), Nimdzi sizes the *whole industry
  including the contracting human-service segments*. Both can be
  right.
- **Industry remains highly fragmented** — top 100 = 19.8% of total,
  same fragmentation pattern Mordor noted (top 100 in services = 15%
  per Mordor). Industry consolidation is happening at the top but
  the long tail remains intact
  ([Nimdzi 100](https://www.nimdzi.com/nimdzi-100-2026)).
- **Polarization by segment** — top 10 grew 3.6%, top 20 grew 3.4%,
  51–100 segment *declined 4.3%* (first negative segment growth since
  2021). Mid-market vendors heavily reliant on public-sector RFPs are
  exposed to budget freezes
  ([Nimdzi 100](https://www.nimdzi.com/nimdzi-100-2026)).
- **Regional revenue concentration**: Top 100 by HQ — Europe 42,
  North America 34, Asia 17, Oceania 7. Top 100 by demand —
  USD 30.6B North America, USD 25.5B Europe, USD 12.6B Asia
  ([Nimdzi 100](https://www.nimdzi.com/nimdzi-100-2026)).
- **Pricing shift away from per-word.** SaaS licensing, platform
  access fees, and hourly productivity models are replacing
  price-per-word as the dominant commercial model. Procurement teams
  anchoring on PPW will misread the actual cost of 2026 platforms
  ([Nimdzi 100](https://www.nimdzi.com/nimdzi-100-2026)).
- **Buyer's market for M&A.** 60% of Nimdzi 100 respondents are
  actively looking to buy. M&A multipliers have compressed; KKR
  acquired Lionbridge from H.I.G. on a free-cash-flow thesis
  rather than growth multiples
  ([Nimdzi 100](https://www.nimdzi.com/nimdzi-100-2026)).
- **AI-only is failing**: clients who tried to use raw AI output
  for "not-for-MT" content saw quality failures and are returning to
  LSPs for expert-in-the-loop validation — the "IKEA-ization"
  pendulum is partially correcting
  ([Nimdzi 100](https://www.nimdzi.com/nimdzi-100-2026)).
- **High-growth verticals are still the regulated ones**: life
  sciences (78.4% of providers offer it), financial/legal (73.0%),
  government (70.3%) — flight to safety into expert-in-the-loop
  domains. Consistent with Mordor's BFSI / pharma growth pattern.

The narrative claims (downsizing of in-house linguists by 20–25%,
"agentic AI" surge, sovereign-AI initiatives) are useful framing for
Advise-mode deliverables but are not load-bearing for sizing.

## Other 2025–2026 industry references

- **Intento State of Translation Automation 2025** — Intento's 9th
  annual industry report, published October 30, 2025, renamed from
  *State of Machine Translation*
  ([Slator](https://slator.com/intento-releases-9th-annual-state-of-translation-automation-2025-industry-report/)).
  Only the press release fragment is captured in our raw/ — the full
  report content is not yet available; this entry is a pointer for
  later ingest when the report or coverage of it is captured.
- **Nimdzi Language Technology Radar 2025** — tracks 660+ langtech
  vendors across 900+ products; categories include TMS, marketplaces,
  MT, integrators, interpreting, ASR, audiovisual, QA, multilingual
  creation, LLMs
  ([Nimdzi Radar 2025](https://www.nimdzi.com/language-technology-radar-report)).
  Geographic distribution: US 34.36% of providers, Germany 6.75%,
  UK 6.44%, France 3.37%
  ([Nimdzi Radar 2025](https://www.nimdzi.com/language-technology-radar-report)).

## Source-quality notes

The MarketsandMarkets MT report
([Machine Translation Market Outlook, Size, Share, Trends, Growth Drivers, Key Players, and Regional Insights](https://www.marketsandmarkets.com/Market-Reports/machine-translation-market-52498643.html))
is in `raw/` but **not used as a citation on this page**. It contains
a clear factual error: it claims "in 2022, Google acquired DeepL,"
which did not happen — DeepL is independent, raised a USD 300M Series
C in November 2025, and remains headquartered in Cologne. The same
report also claims Microsoft acquired Systran in 2021, which is also
false (Systran was acquired by ChallengeOne / Korean investors in
2014, not Microsoft). Treat that source's specific factual claims as
unreliable; the segment taxonomy and generic trend framing are
non-load-bearing and duplicate what Mordor covers with sourcing.

The Forrester Wave blog is a teaser for a paywalled report; it gives
the vendor list and Forrester's framing of the market but no scoring
or trade-offs. The full Wave is needed for vendor-specific
recommendations.

## Open questions

- TMS market sizing — neither Mordor report sizes the TMS layer
  separately, and the Forrester teaser doesn't either; if a client
  needs TMS-specific TAM, this requires a different source.
- Interpretation-only sub-market sizing (OPI / VRI / on-site) is
  bundled in the services figure but not broken out.
- Vendor revenue-share data for either market — Mordor names leaders
  but does not split shares.

## Sources

- [Machine Translation Market - Size, Companies & Share](https://www.mordorintelligence.com/industry-reports/machine-translation-market) — Mordor Intelligence MT market report, 2025-2031 framing, captured 2026-05-01.
- [Translation Service Market Size, Drivers & Opportunities](https://www.mordorintelligence.com/industry-reports/translation-services-market) — Mordor Intelligence translation services market report, 2025-2031 framing, captured 2026-05-01.
- [Announcing The Forrester Wave™_ Translation Management Systems, Q3 2025, Our Inaugural Evaluation Of The Market](https://www.forrester.com/blogs/announcing-the-first-forrester-wave-translation-management-systems-q3-2025/) — Forrester teaser blog for paywalled Wave; vendor list and market framing only.
- [Machine Translation Market Outlook, Size, Share, Trends, Growth Drivers, Key Players, and Regional Insights](https://www.marketsandmarkets.com/Market-Reports/machine-translation-market-52498643.html) — MarketsandMarkets MT report; cited only as a source-quality cautionary note, not for factual claims (contains Google-acquired-DeepL falsehood).
- [The 2026 Nimdzi 100](https://www.nimdzi.com/nimdzi-100-2026) — Nimdzi's 2026 industry ranking + sizing; whole-industry framing (USD 72.6B 2025), segment polarization, M&A activity, pricing-model shift, IKEA-ization framing.
- [2025 Language Technology Radar Report](https://www.nimdzi.com/language-technology-radar-report) — Nimdzi Language Technology Radar; 660+ vendors / 900+ products tracked across 10 categories; geographic distribution; LLM/agentic-AI framing.
- [Intento Releases 9th Annual “State of Translation Automation 2025” Industry Report](https://slator.com/intento-releases-9th-annual-state-of-translation-automation-2025-industry-report/) — Slator coverage of Intento's industry report; only press-release fragment captured, full data not yet available.
