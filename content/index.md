# Wiki index

## Comparisons
- [[comparisons/mt-engines]] — candidate set of MT engines (8 from Transcy + Mordor MT additions: Amazon, Azure, NLLB, Systran, RWS Language Weaver, LILT, Lingvanex, ModernMT, Lara, Custom.MT meta-platform, etc.); deployment + residency annotations; on-prem short list; **underlying technology stack (NMT / hybrid NMT-SMT / LLM-based / SLM / agentic MT)** and **capability matrix (doc-level, speech, OCR, NER, PII, custom, adaptive, glossary, human, code-switching)**; **benchmark leaders 2022→2025 (Intento AMTA 2022 → WMT 2023/24/25; Gemini 2.5 Pro / Claude / GPT now leading vs. commercial NMT incumbents)**.
- [[comparisons/translation-platforms]] — TMS / CAT / AI-translation-services vendor catalog; Forrester Wave Q3 2025 cohort, Gartner category, Redokun pricing-transparent list, **Nimdzi 100 2026 cohort with M&A activity**, **LSP-built proprietary AI platforms (Acolad Lia, Welocalize Opal, Lionbridge Aurora, Argos MosAIQ, RWS Evolve)**, **meta-platform/aggregator layer (Custom.MT, Intento, ModelFront)**; deployment / residency annotations.
- [[comparisons/translation-market-sizing]] — MT vs. translation-services vs. TMS vs. **whole-language-industry (Nimdzi 100)** market scopes; segment shares (technology, deployment, vertical, geography); drivers/restraints; Q4 2025–Q1 2026 moves; **Nimdzi 2026 sizing (USD 72.6B 2025 → USD 76.1B 2030, fragmentation, mid-tier 51-100 decline)**.
- [[comparisons/mt-evaluation]] — how MT systems are *actually* benchmarked in 2026; **WMT 2023→2025 arc** (LLMs gradually winning, automatic-metric bias, ESA+MQM protocols, difficulty sampling); **Intento+e2f AMTA 2022 commercial benchmark** (31 engines × 9 industries × 11 pairs); leader rosters; NLLB on-prem-quality reality check.

## Patterns
- [[patterns/on-prem-translation]] — when on-prem translation infrastructure dominates (sensitive data, air-gap, sub-100ms latency, sustained volume) vs. when SaaS wins; hybrid topologies; build-mode candidate engines; **explicit out-of-scope list (ModernMT, DeepL Enterprise, hyperscaler MT)**; **Custom.MT closed-circuit framing**; **sovereign-AI framing from Nimdzi 100**; **concrete Lingvanex hardware-sizing data (Intel i7, 32GB RAM, 8GB VRAM, 100GB disk)**; **WMT25 NLLB-quality reality check (competitive on low-resource, weak on mainstream)**.

## Antipatterns
- [[antipatterns/translation-procurement]] — architectural traps (SaaS fallback, "private cloud" as on-prem, meta-platform routing, speech/OCR egress) and procurement traps (vendor-published rankings as findings, cherry-picked stats, TMS lock-in, layer-conflation, ranking on quality before deployment, solo operator buying enterprise infra, **IKEA-ization of localization**, **vibe-coding LSP tools**, **procuring on automatic-metric leaderboards (WMT metric-bias evidence)**).

## Technologies
- [[technologies/transcy]] — Shopify-focused MT meta-platform; BYOK vs. pay-per-use models; where it fits and doesn't.
- [[technologies/systran]] — Enterprise MT vendor (ChapsVision); on-prem Pure Neural Server, 60+ languages / 150 pairs, domain models in regulated sectors, US defense / intelligence track record.
- [[technologies/language-weaver]] — RWS's enterprise MT platform; SaaS / on-prem (Edge) / hybrid; 3,500+ language combinations; Language Weaver Pro 100B-param model with Cohere (2026-03-25).
- [[technologies/lilt]] — US enterprise / public-sector MT platform; bare-metal-capable; only cohort vendor with human linguist verification in same SKU; FDA CFR Part 11 certified.
- [[technologies/apptek]] — Research-led NMT vendor; text + speech; on-prem + cloud; strong low-resource language coverage (Pashto, Dari, Tigrinya, etc.).
- [[technologies/tilde-mt]] — EU (Latvian) MT vendor; SaaS + on-prem; 40+ engines + LLMs; Trados/MemoQ plugins; integrated with EC WEB-T.
- [[technologies/omniscien]] — Niche enterprise MT (Language Studio); SaaS + on-prem; Hybrid Deep NMT/SMT approach; unlimited-volume subscription pricing.
- [[technologies/pangeanic]] — EU (Spanish) NLP/AI vendor; on-prem incl. air-gapped; Deep Adaptive AI Translation; task-specific Small Language Models for local infra.
- [[technologies/modernmt]] — Translated's (IT) adaptive MT engine; cloud-only SaaS; document-level + real-time human-in-the-loop learning; IDC MarketScape Leader 2023; 200 languages.
