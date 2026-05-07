# Wiki index

## Comparisons
- [[comparisons/mt-engines]] — candidate set of MT engines (8 from Transcy + Mordor MT additions: Amazon, Azure, NLLB, Systran, RWS Language Weaver, LILT, Lingvanex, etc.); deployment + residency annotations; on-prem short list; **underlying technology stack (NMT / hybrid NMT-SMT / LLM-based / SLM)** and **capability matrix (doc-level, speech, OCR, NER, PII, custom, adaptive, glossary, human, code-switching)**.
- [[comparisons/translation-platforms]] — TMS / CAT / AI-translation-services vendor catalog; Forrester Wave Q3 2025 cohort, Gartner category, Redokun pricing-transparent list; deployment / residency annotations.
- [[comparisons/translation-market-sizing]] — MT vs. translation-services vs. TMS market scopes; segment shares (technology, deployment, vertical, geography); drivers/restraints; Q4 2025–Q1 2026 moves.

## Patterns
- [[patterns/on-prem-translation]] — when on-prem translation infrastructure dominates (sensitive data, air-gap, sub-100ms latency, sustained volume) vs. when SaaS wins; hybrid topologies; build-mode candidate engines.

## Antipatterns
- [[antipatterns/translation-procurement]] — architectural traps (SaaS fallback, "private cloud" as on-prem, meta-platform routing, speech/OCR egress) and procurement traps (vendor-published rankings as findings, cherry-picked stats, TMS lock-in, layer-conflation, ranking on quality before deployment, solo operator buying enterprise infra).

## Technologies
- [[technologies/transcy]] — Shopify-focused MT meta-platform; BYOK vs. pay-per-use models; where it fits and doesn't.
- [[technologies/systran]] — Enterprise MT vendor (ChapsVision); on-prem Pure Neural Server, 60+ languages / 150 pairs, domain models in regulated sectors, US defense / intelligence track record.
- [[technologies/language-weaver]] — RWS's enterprise MT platform; SaaS / on-prem (Edge) / hybrid; 3,500+ language combinations; Language Weaver Pro 100B-param model with Cohere (2026-03-25).
- [[technologies/lilt]] — US enterprise / public-sector MT platform; bare-metal-capable; only cohort vendor with human linguist verification in same SKU; FDA CFR Part 11 certified.
- [[technologies/apptek]] — Research-led NMT vendor; text + speech; on-prem + cloud; strong low-resource language coverage (Pashto, Dari, Tigrinya, etc.).
- [[technologies/tilde-mt]] — EU (Latvian) MT vendor; SaaS + on-prem; 40+ engines + LLMs; Trados/MemoQ plugins; integrated with EC WEB-T.
- [[technologies/omniscien]] — Niche enterprise MT (Language Studio); SaaS + on-prem; Hybrid Deep NMT/SMT approach; unlimited-volume subscription pricing.
- [[technologies/pangeanic]] — EU (Spanish) NLP/AI vendor; on-prem incl. air-gapped; Deep Adaptive AI Translation; task-specific Small Language Models for local infra.
