---
type: comparison
tags:
  - topic/translation
  - mode/advise
  - mt
  - vendor-evaluation
sources:
  - Transcy Translation Engines_ Which One Best Suits You_
  - Machine Translation Market - Size, Companies & Share
  - Translation Service Market Size, Drivers & Opportunities
  - (11) Why You Should Choose an On-prem Translation System for Corporate Translation
  - Comparing Enterprise AI Translation Software in 2026_ Security, Deployment and Professional Accuracy, Comparing Enterprise AI Translation Software in 2026
  - Automated translation
  - SYSTRAN Server On Premise
  - SYSTRAN translate Server
  - Language Weaver, Translation Technology
  - Machine Translation (MT) _ AppTek.ai Speech Technologies
  - Machine Translation Features _ Tilde MT
  - Machine Translation with AI at scale_ Flexible, Private, Adaptive
  - Language Studio Enterprise Translation Server
  - Enterprise AI Translation Platform
  - On-premise Machine Translation
last_updated: 2026-05-07
---

# Machine translation engines

A starting market view for evaluating commercial machine-translation
(MT) engines. Built initially from a single vendor-marketing source
([Transcy's engine guide](https://transcy.io/blog/translation-engine-guide/)),
which is enough to enumerate the candidate set but **not enough to
recommend between them**. Independent benchmarks needed before any
"best for X" claim is treated as fact — see [[#Open questions]].

## Source-quality caveat

The "best for" / "highlights" columns below come from a vendor
positioning itself as a meta-platform that resells access to all 8
engines. Transcy has no incentive to disparage any of them, but also
no incentive to be objective. Treat these as **Transcy's claims** to
be confirmed or contradicted by independent sources, not as findings.

## Engine candidate set

The original 8 engines came from the Transcy source
([Transcy](https://transcy.io/blog/translation-engine-guide/)),
which is e-commerce-merchant-shaped. The Mordor MT market report
([Mordor MT](https://www.mordorintelligence.com/industry-reports/machine-translation-market))
names additional vendors in its competitive-landscape section that
were missing from the Transcy list — those are appended below.
Deployment model and data-residency posture below are *my* annotations
based on each engine's general public posture, not from the sources —
verify per-client before recommending.

### Transcy-listed engines (e-commerce framing)

| Engine | Vendor | Language coverage | Deployment | Data residency | "Best for" (per Transcy) |
|---|---|---|---|---|---|
| Google Translate | Google | 244+ | SaaS only | Global; limited EU-only options | Free tier, broad coverage |
| DeepL | DeepL SE (DE) | 30+ | SaaS; on-prem available (DeepL On-Premise) | EU-based, strong GDPR posture | European languages |
| OpenAI (GPT-4 / 4o family) | OpenAI | No fixed list | SaaS only (Azure OpenAI offers regional deploys) | US default; EU via Azure | Marketing / nuanced content |
| Baidu Translate | Baidu (CN) | 200+ | SaaS only | China-based — sovereignty implications outside CN | Chinese & character-based languages |
| Gemini | Google | No fixed list | SaaS only | Global; Vertex AI offers regional deploys | SEO content, Google ecosystem |
| Yandex Translate | Yandex (RU) | 90+ | SaaS only | Russia-based — sanctions / sovereignty implications | Russian / Slavic languages |
| Grok | xAI | 270+ | SaaS only | US default | Creative / branded content |
| DeepSeek | DeepSeek (CN) | 100+ | SaaS; weights are open — self-host viable | Self-host eliminates residency issue | Technical / formal documentation |

### Additional engines (named in Mordor MT competitive landscape)

| Engine | Vendor | Deployment | Data residency | Positioning |
|---|---|---|---|---|
| Amazon Translate | AWS | SaaS only (AWS regions); FedRAMP High, AWS GovCloud (US-West) for US gov workloads ([ChapsVision review](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/)) | US/EU/APAC AWS regions; no on-prem | Cloud-bundled; 75 languages ([ChapsVision review](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/)); Custom Terminology launched Oct 2025, cuts post-editing up to 40% ([Mordor MT](https://www.mordorintelligence.com/industry-reports/machine-translation-market)) |
| Microsoft Azure Translator | Microsoft | SaaS only (Azure regions); Azure Government for US federal (FedRAMP, DoD) ([ChapsVision review](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/)) | Azure-region-bound; sovereign-cloud variants | 100+ languages, Custom Translator for domain models from client corpora ([ChapsVision review](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/)); USD 150M committed Dec 2025 to add 25 African / indigenous languages by mid-2026 ([Mordor MT](https://www.mordorintelligence.com/industry-reports/machine-translation-market)) |
| Google Cloud Translation Advanced | Google | SaaS only (GCP); no on-prem available ([ChapsVision review](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/)) | GCP regions; HIPAA, SOC 2, GDPR | **189 languages — broadest coverage** in the cohort; Translation LLM (Gemini-powered), Adaptive Translation, AutoML; Translation Hub interface supports human review across 135 languages ([ChapsVision review](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/)) |
| Meta NLLB | Meta (open) | Open weights — self-host | Self-host eliminates residency issue | 200 languages; commoditizes pricing; BLEU below 20 for numerous low-resource pairs ([Mordor MT](https://www.mordorintelligence.com/industry-reports/machine-translation-market)) |
| OpenNMT, Marian | Open-source (university / community) | Self-host | Self-host | Companies with ML talent report 70-80% cost savings vs. paid APIs ([Mordor MT](https://www.mordorintelligence.com/industry-reports/machine-translation-market)) |
| Systran ([[../technologies/systran]]) | SYSTRAN by ChapsVision | On-prem (Pure Neural Server / translate Server), private cloud, SaaS ([SYSTRAN](https://www.systransoft.com/translation-products/translate-server/)) | Self-host viable; GDPR + ISO 27001, no data storage ([ChapsVision review](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/)) | 60+ languages, 150 pairs; domain models in legal / defense / finance / pharma / industrial; documented track record in US defense & intelligence ([ChapsVision review](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/)) |
| RWS Language Weaver ([[../technologies/language-weaver]]) | RWS Holdings | SaaS (Cloud), on-prem (Edge), hybrid; Edge supports Kubernetes autoscaling ([ChapsVision review](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/)) | Self-host viable; GDPR + ISO 27001:2013, AES-256, TLS 1.2, SAML SSO | **3,500+ language combinations on Edge — broadest in the on-prem-capable cohort**; Language Weaver Pro launched 2026-03-25 with Cohere (100B+ params); default first-pass for 55% of content in RWS TMS ([Mordor TSM](https://www.mordorintelligence.com/industry-reports/translation-services-market), [ChapsVision review](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/)) |
| LILT ([[../technologies/lilt]]) | LILT Inc. | Public cloud, private cloud, on-prem, **bare metal** (air-gap-capable) ([ChapsVision review](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/)) | US-led; SOC 2 Type II, ISO 9001/17100/18587, GDPR, HIPAA, **FDA CFR Part 11**, Cyber Essentials | Adaptive LLMs per client; **only vendor in cohort with human-verified translation in same SKU**; defense / regulated focus ([ChapsVision review](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/)) |
| DeepL Enterprise | DeepL SE (DE) | SaaS-only (cloud); BYOK encryption-key option ([ChapsVision review](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/)) | EU-based, GDPR + ISO 27001 + SOC 2 Type II + HIPAA | 100+ languages; glossaries only (no domain-model training); 200K+ business clients incl. 50% of Fortune 500 ([ChapsVision review](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/)) — **note: contradicts Transcy row above which described DeepL as having an on-prem offering; the ChapsVision review explicitly classifies DeepL Enterprise as cloud-only** |
| Unbabel | TransPerfect (acquired 2025) | SaaS | US/EU | Customer-support focus; AI + human workflows |
| Lingvanex On-Premise | Nordicwise / Lingvanex | On-prem (vendor's primary positioning) + Cloud API ([Lingvanex on-prem](https://lingvanex.com/products/on-premise-machine-translation/)) | Self-host | 100+ languages claimed; offers a 20-year-encrypted perpetual licence as alternative to subscription ([Lingvanex on-prem](https://lingvanex.com/products/on-premise-machine-translation/)); vendor-marketing source — not independently benchmarked here |
| IBM Watson Language Translator | IBM | SaaS | IBM Cloud regions | Named as one of 5 industry leaders in Mordor MT ([Mordor MT](https://www.mordorintelligence.com/industry-reports/machine-translation-market)) |
| Tencent Cloud MT | Tencent (CN) | SaaS | China-based — sovereignty implications outside CN | Named in Mordor competitive landscape ([Mordor MT](https://www.mordorintelligence.com/industry-reports/machine-translation-market)) |
| PROMT | PROMT Ltd. | SaaS + on-prem | Russia-based — sanctions / sovereignty risk | Named in Mordor competitive landscape ([Mordor MT](https://www.mordorintelligence.com/industry-reports/machine-translation-market)) |
| AppTek Neural MT Platform ([[../technologies/apptek]]) | AppTek | On-prem + cloud SaaS; real-time API + batch ([AppTek](https://www.apptek.ai/technology/machine-translation)) | US-led | **Text + speech MT** in same product; ~80 languages incl. low-resource (Pashto, Dari, Tigrinya, Hausa, Kazakh); document-level translation; in-sentence code-switching support ([AppTek](https://www.apptek.ai/technology/machine-translation)) |
| Omniscien Language Studio ([[../technologies/omniscien]]) | Omniscien Technologies | SaaS (Secure Cloud), on-prem (LSETS), on-prem (Data Center Platform — billion-words/day scale) ([Omniscien](https://omniscien.com/products/language-studio/language-studio-features/)) | Self-host viable; GDPR-by-design via on-prem | **Hybrid Deep NMT/SMT** approach (rare in 2026); off-the-shelf Industry MT engines (legal, medical, etc.); on-prem editions priced as unlimited-volume subscription ([Omniscien LSETS](https://omniscien.com/products/language-studio/enterprise-translation-server/)) |
| Tilde MT ([[../technologies/tilde-mt]]) | Tilde (LV) | SaaS by default; on-prem and private-cloud available; 30+ years of Tilde MT R&D ([Tilde](https://tilde.ai/translate/tilde-machine-translation/features/)) | EU-based; "no storage / no analysis" data-handling on cloud SaaS | 40+ engines + LLMs; Trados / MemoQ plugins; integrated with EC WEB-T (Drupal/Joomla/WordPress/WooCommerce plugins) ([Tilde](https://tilde.ai/translate/tilde-machine-translation/features/), [EC WEB-T](https://website-translation.language-tools.ec.europa.eu/automated-translation_en)) |
| Pangeanic ([[../technologies/pangeanic]]) | Pangeanic (ES) | Managed Private Cloud (ECO); On-prem incl. air-gapped; task-specific Small Language Models for local infra ([Pangeanic](https://pangeanic.com/machine-translation)) | EU-based; private-SaaS option | 200+ languages; **Deep Adaptive AI Translation (DAAIT)** real-time post-edit learning; PII anonymisation as pre-translation step; Gartner Hype Cycle mentions 2023+2024 ([Pangeanic](https://pangeanic.com/machine-translation)); EC WEB-T integrated ([EC WEB-T](https://website-translation.language-tools.ec.europa.eu/automated-translation_en)) |
| ModernMT | Translated (IT) | SaaS API (subscription) | EU-based vendor | First real-time **adaptive** MT product; Transformer architecture; learns from each user interaction; 200+ languages; integrated with EC WEB-T ([EC WEB-T](https://website-translation.language-tools.ec.europa.eu/automated-translation_en)) |
| eTranslation | EU Commission DG-T | SaaS (free for eligible orgs) | EU-only | EC's own NMT service; exclusive to EU institutions, public administrations, SMEs, universities, NGOs and Digital Europe Programme projects; covers 30+ languages incl. all EU official languages; 20MB request limit ([EC WEB-T](https://website-translation.language-tools.ec.europa.eu/automated-translation_en)) |

The "Deployment" and "Data residency" columns are the procurement-
relevant ones for `mode/advise`. The "Best for" column is what the
*source* offers; do not propagate it without confirmation.

## Underlying technology stack

The capability matrix below surfaces *what* each engine can do; this
section surfaces *how* it does it. Architecture is rarely the
procurement filter (deployment + certifications is — see the
threshold-criterion section below) but it's load-bearing for two
specific questions: hardware footprint for on-prem, and where the
engine sits on the NMT → LLM transition currently underway in
2026.

Cell legend: ✓ documented in source · — absent in source · **?** unknown.
"Architecture family" is best-effort from each vendor's own
positioning; the boundary between "NMT" and "LLM-based MT" is fuzzy
in 2026 and getting fuzzier.

| Engine | Architecture family | Adaptive learning | Foundation-model partner | OSS / proprietary | Notes |
|---|---|---|---|---|---|
| Google Translate (consumer) | NMT (legacy) → Translation LLM (Advanced tier) | ? | Gemini (Advanced tier) | Proprietary | Hyperscaler |
| Google Cloud Translation Advanced | LLM-based (Translation LLM) + AutoML custom models | ✓ Adaptive Translation | Gemini ([ChapsVision review](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/)) | Proprietary | Foundation-model-based |
| DeepL Enterprise | NMT (proprietary, EU-trained) | — | None disclosed | Proprietary | Pre-LLM-era architecture |
| OpenAI GPT-4 / 4o | LLM (general-purpose, used as MT) | — | (Is the foundation model) | Proprietary | Translation as emergent capability |
| Gemini | LLM (general-purpose, used as MT) | ? | (Is the foundation model) | Proprietary | Translation as emergent capability |
| Grok | LLM (general-purpose) | ? | (Is the foundation model) | Proprietary | Translation as emergent capability |
| DeepSeek | LLM (general-purpose; open weights) | ? | (Is the foundation model) | Open weights | "LLM-style translation, not dedicated MT" — see candidate-set table |
| Baidu / Yandex / Tencent | NMT (regional incumbents) | ? | ? | Proprietary | Architecture details not in our sources |
| Amazon Translate | NMT | — (glossaries only) | None disclosed | Proprietary | Pre-LLM-era architecture |
| Microsoft Azure Translator | NMT + Custom Translator (domain models from corpora) | ✓ via Custom Translator | None disclosed | Proprietary | Pre-LLM-era architecture |
| Meta NLLB | NMT (Transformer encoder-decoder) | — | (Is the model) | **Open weights** | The OSS workhorse for sovereign deploy |
| OpenNMT | NMT framework | — | n/a | **Open-source** | Toolkit, not a model — bring your own training |
| Marian | NMT framework | — | n/a | **Open-source** | Toolkit, not a model |
| M2M100 | NMT (multilingual) | — | (Is the model) | **Open weights** | Meta-released multilingual NMT |
| SYSTRAN ([[../technologies/systran]]) | **Transformer-family NMT**, "in a flavor and size specifically designed for MT" ([SYSTRAN](https://www.systransoft.com/translation-products/translate-server/)); reseller mentions Neural Fuzzy Adaptation (NFA) for real-time output adaptation ([Lingo360](https://www.translationsoftware4u.com/systran-server-on-premise/)) | ✓ NFA (per reseller, not on SYSTRAN's own page) | None disclosed | Proprietary | Pure-NMT bet; Model Studio for custom models |
| RWS Language Weaver ([[../technologies/language-weaver]]) | NMT (Fast tier) → **LLM-based at top tier**: Pro is a 100B+ param model, partnership with Cohere, launched 2026-03-25 ([ChapsVision review](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/)) | ✓ Continuous adaptation from corrections | **Cohere** (Pro tier) | Proprietary | First mainstream MT vendor to ship a 100B+ param branded MT-LLM |
| LILT ([[../technologies/lilt]]) | **Adaptive LLMs** per client; supports BYO foundation model (Gemini / GPT / Claude) ([LILT](https://lilt.com/)) | ✓ Continuous, real-time | BYO (Gemini, GPT, Claude) or LILT's own | Proprietary | Most explicit "LLM-based MT" positioning; agentic platform framing |
| AppTek ([[../technologies/apptek]]) | NMT with attention-based deep neural networks; direct HMMs combined with deep neural networks; multilingual + end-to-end speech-to-speech models ([AppTek](https://www.apptek.ai/technology/machine-translation)) | ? | None disclosed | Proprietary | Research-led; only vendor in cohort using HMMs alongside NMT |
| Tilde MT ([[../technologies/tilde-mt]]) | NMT + LLMs as a 40+ engine portfolio; LLM-augmented features like summarisation and register selection ([Tilde](https://tilde.ai/translate/tilde-machine-translation/features/)) | ? | None disclosed; uses LLMs but doesn't name them | Proprietary | NMT-and-LLMs side-by-side, not a single architecture |
| **Omniscien Language Studio** ([[../technologies/omniscien]]) | **Hybrid Deep NMT/SMT** — explicitly retains SMT alongside NMT ([Omniscien LSETS](https://omniscien.com/products/language-studio/enterprise-translation-server/)) | — (off-the-shelf industry domain models; custom training available) | None disclosed | Proprietary | **Contrarian holdout: only cohort vendor still running SMT in production in 2026** |
| **Pangeanic** ([[../technologies/pangeanic]]) | NMT + **task-specific Small Language Models (SLMs)** designed for local infrastructure ([Pangeanic](https://pangeanic.com/machine-translation)) | ✓ DAAIT — real-time learning from human-corrected style; on-the-fly or after-review training cycles | None disclosed (in-house SLMs) | Proprietary | **Sovereign-deploy LLM answer: SLM as the on-prem-friendly LLM-shape** |
| ModernMT | Transformer architecture; learns from each user interaction in real-time ([EC WEB-T](https://website-translation.language-tools.ec.europa.eu/automated-translation_en)) | ✓ Real-time adaptive | None disclosed | Proprietary | First commercial real-time adaptive MT |
| eTranslation | NMT (architecture not detailed) | — | None disclosed | Proprietary (EU Commission) | EU-public-sector option |
| Lingvanex | NMT (architecture not detailed) | ? customisation available | None disclosed | Proprietary | On-prem-first vendor |
| IBM Watson Language Translator | NMT | ? | None disclosed | Proprietary | Hyperscaler-adjacent |
| PROMT | NMT (modern); historically rule-based / statistical | ? | None disclosed | Proprietary | Russia-based — sanctions risk |
| Unbabel | NMT + human network | — | None disclosed | Proprietary | Acquired by TransPerfect 2025 |

### Where the cohort sits on the NMT → LLM transition

This is the most informative axis to read out of the table.

- **Foundation-model-based MT** — Google Cloud (Translation LLM,
  Gemini-powered), RWS Language Weaver Pro (Cohere, 100B+ params),
  LILT (BYO Gemini/GPT/Claude). 2025–2026 moves; not present in
  earlier captures. This is the leading edge.
- **General-purpose LLMs used *as* MT** — OpenAI, Gemini direct,
  Grok, DeepSeek. Translation is an emergent capability rather than
  a dedicated product. Quality is competitive on major language
  pairs; adapter / customisation story is weaker.
- **Pure-NMT (Transformer-era)** — SYSTRAN, AppTek, ModernMT, Tilde
  (where it's not LLM-augmented), DeepL, Amazon, Azure, NLLB, M2M100,
  IBM, Unbabel. Still the workhorse architecture. Mature, predictable
  hardware footprint.
- **NMT + SLM hybrid (sovereign-deploy answer)** — Pangeanic. SLMs
  give "LLM-level fluency" with the deterministic control and
  hardware footprint that LLMs don't. Pangeanic is the only vendor in
  our captures positioning SLMs explicitly for on-prem MT.
- **Hybrid Deep NMT/SMT (legacy retained)** — Omniscien. The only
  cohort holdout still running SMT alongside NMT in 2026; positioned
  as a quality/control mechanism, not a transitional artifact. Whether
  that's a real differentiator or marketing-of-legacy-stack is an
  open question.
- **Pure rule-based MT** — **absent from the cohort**. PROMT
  historically had rule-based engines but its current product is
  NMT. Rule-based MT survives in academic and constrained-domain
  niches (specific legal-codex translators, internal enterprise
  systems) but no general-purpose vendor in our captures still ships
  it as a primary product.

### What this means for the wiki's `mode/build` recommendations

Solo operators picking an on-prem engine in 2026 have a more useful
choice than "OSS NMT vs. Lingvanex":

- **NMT (NLLB / OpenNMT / Marian)** — bounded, predictable hardware,
  weak on low-resource pairs, no adapter quality.
- **Foundation-model MT (RWS Pro, Google LLM, LILT BYO)** — best
  quality on major pairs but cloud-only or expensive to run on-prem.
- **SLM (Pangeanic)** — emerging answer to "I want LLM quality with
  NMT-shaped hardware". Worth tracking; verify SLM specifics
  (parameter count, supported pairs) before recommending — see the
  open question on [[../technologies/pangeanic]].
- **Hybrid NMT/SMT (Omniscien)** — only relevant if the legacy SMT
  component genuinely helps domain control; otherwise plain NMT is
  simpler.

## Capability matrix

The candidate-set tables above slice on deployment and residency —
the threshold-criterion dimensions for procurement (see below). This
matrix slices on **capability differentiators** that would otherwise
stay buried in vendor-page prose. Useful for "which engines do X?"
queries.

Cell legend: ✓ documented in source · — absent in source / not
offered · **?** unknown / not in our sources.

Capability columns:

- **Doc-level** — Document-level translation (uses full-document
  context to disambiguate genders, pronouns, references; goes beyond
  sentence-by-sentence)
- **Speech** — Audio-in / speech-to-speech translation in the same
  product
- **OCR** — Scanned-document translation in the same product
- **NER** — Named-entity transliteration / handling (proper names,
  places, codes)
- **PII** — PII anonymisation / redaction as a pre- or
  post-translation step
- **Custom** — Custom-model training on customer corpora (beyond
  glossaries / terminology lists)
- **Adaptive** — Online adaptive learning from user corrections in
  real time
- **Glossary** — Terminology / glossary database
- **Human** — Human-verified translation routed through the same SKU
- **Code-sw** — In-sentence code-switching support (mixed-language
  input)

| Engine | Doc-level | Speech | OCR | NER | PII | Custom | Adaptive | Glossary | Human | Code-sw |
|---|---|---|---|---|---|---|---|---|---|---|
| Google Translate | ? | — | — | ? | — | — | — | — | — | ? |
| Google Cloud Translation Advanced | ? | — | — | ? | — | ✓ AutoML | ✓ Adaptive Translation | ✓ | ✓ Translation Hub (135 langs) | ? |
| DeepL Enterprise | ? | — | — | ? | — | — | — | ✓ glossaries | — | ? |
| OpenAI / Gemini / Grok / DeepSeek | ✓ via context | — | — | ? | ? prompt-driven | — | — | — | — | ✓ via prompt |
| Baidu / Yandex / Tencent | ? | ? | ? | ? | ? | ? | ? | ? | — | ? |
| Amazon Translate | — | — | — | ? | — | — Custom Terminology only | — | ✓ Custom Terminology | — | ? |
| Microsoft Azure Translator | ? | ? Speech service is separate | ? | ? | — | ✓ Custom Translator | — | ✓ | — | ? |
| Meta NLLB | — | — | — | ? | — | ✓ via fine-tuning | — | — | — | ? |
| OpenNMT / Marian / M2M100 | ✓ if you train it | — | — | ? | — | ✓ (frameworks) | — | — | — | ? |
| **SYSTRAN** | ? | ✓ Speech-to-Text translation ([SYSTRAN](https://www.translationsoftware4u.com/systran-server-on-premise/)) | ✓ built-in PDF + OCR for scanned docs ([SYSTRAN](https://www.translationsoftware4u.com/systran-server-on-premise/)) | ✓ Do-Not-Translate (DNT) terms; user dictionaries handle inflection / gender / pluralization ([SYSTRAN](https://www.translationsoftware4u.com/systran-server-on-premise/)) | — | ✓ Model Studio + user dictionaries ([SYSTRAN](https://www.systransoft.com/translation-products/translate-server/)) | ✓ Neural Fuzzy Adaptation (per reseller; not on SYSTRAN's page) ([Lingo360](https://www.translationsoftware4u.com/systran-server-on-premise/)) | ✓ user dictionaries | — | ? |
| **RWS Language Weaver** | ? | — | — | ? | — | ✓ continuous adaptation | ✓ corrections-based ([ChapsVision review](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/)) | ? | — (RWS group offers human services separately) | ? |
| **LILT** | ? | — | — | ? | — | ✓ adaptive LLMs per client | ✓ continuous from human-AI interactions ([LILT](https://lilt.com/)) | ✓ glossaries + TM | **✓ Verify product — only vendor in ChapsVision cohort** ([ChapsVision review](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/)) | ? |
| **AppTek** | **✓ explicit document-level translation for gender/pronoun/reference handling** ([AppTek](https://www.apptek.ai/technology/machine-translation)) | ✓ speech-to-speech translation; real-time + batch ([AppTek](https://www.apptek.ai/technology/machine-translation)) | — | **✓ Named Entity Transliteration as a named feature** ([AppTek](https://www.apptek.ai/technology/machine-translation)) | — | ✓ fast domain adaptation to customer TM ([AppTek](https://www.apptek.ai/technology/machine-translation)) | ? | ? | — | **✓ in-sentence code-switching (e.g. mixed Ukrainian/Russian)** ([AppTek](https://www.apptek.ai/technology/machine-translation)) |
| **Tilde MT** | ? | ? Tilde does speech tech but separate product | ? | ? | — | ✓ custom MT engines on customer data ([Tilde](https://tilde.ai/translate/tilde-machine-translation/features/)) | ? | ✓ glossaries shared across organisation ([Tilde](https://tilde.ai/translate/tilde-machine-translation/features/)) | — | ? |
| **Omniscien Language Studio** | ? | — | ? | ? | — | ✓ Custom MT engines on customer data + Data Synthesis tools ([Omniscien](https://omniscien.com/products/language-studio/enterprise-translation-server/)) | — (off-the-shelf industry domains + custom training) | ✓ industry domain engines for terminology context ([Omniscien](https://omniscien.com/products/language-studio/enterprise-translation-server/)) | — | ? |
| **Pangeanic** | ? | — | — | ✓ NER as part of NLP pipeline ([Pangeanic](https://pangeanic.com/machine-translation)) | **✓ PII Discovery & Anonymisation as pre-translation step — only vendor in our captures bundling this with MT** ([Pangeanic](https://pangeanic.com/machine-translation)) | ✓ DAAIT customised per client + bespoke NLP engineering ([Pangeanic](https://pangeanic.com/machine-translation)) | **✓ DAAIT real-time adaptive learning from corrections** ([Pangeanic](https://pangeanic.com/machine-translation)) | ? | — | ? |
| ModernMT | ? | — | — | ? | — | ✓ adapts to customer data | ✓ real-time from each interaction ([EC WEB-T](https://website-translation.language-tools.ec.europa.eu/automated-translation_en)) | ? | — | ? |
| eTranslation | ? | — | — | ? | — | ? | — | ? | — | ? |
| Lingvanex | ? | — | ✓ digital + searchable PDFs (image-only PDFs not supported) ([Lingvanex on-prem](https://lingvanex.com/products/on-premise-machine-translation/)) | ? | — | ✓ training/customisation per client request ([Lingvanex on-prem](https://lingvanex.com/products/on-premise-machine-translation/)) | ? | ? | — | ? |
| IBM Watson | ? | ? IBM Watson speech is separate | ? | ? | — | ? | ? | ? | — | ? |
| PROMT | ? | ? | ? | ? | ? | ? | ? | ? | — | ? |
| Unbabel | ? | — | — | ? | — | — | — | — | ✓ AI + human (legacy product) | ? |

### Capability differentiators that stand out

Reading down the columns:

- **PII anonymisation bundled with MT** — Pangeanic alone in our
  captures. Structurally interesting because it changes the
  trust-boundary math: redaction-before-translation can let
  cloud-MT carry traffic that on-prem would otherwise be required
  for. None of the other 6 dedicated-MT vendors surface this; flag
  for verification (vendors may do it without marketing it).
- **NER as a *named feature*** — AppTek (Named Entity
  Transliteration) and Pangeanic (NER as pipeline step) explicitly.
  Most others certainly handle named entities under the hood but
  don't expose it as a feature.
- **Speech translation in the same product** — AppTek (speech-to-
  speech), SYSTRAN (Speech-to-Text translation). For the rest,
  speech is a separate product line (Microsoft, IBM, Tilde) or not
  offered.
- **Document-level translation as a named feature** — AppTek
  explicitly. Others certainly do sentence-context handling but
  document-level is rarely surfaced as a differentiator.
- **In-sentence code-switching** — AppTek alone in our captures.
  Niche but load-bearing for some government / multilingual-region
  workflows.
- **Adaptive learning** — LILT, RWS Language Weaver, ModernMT,
  Pangeanic (DAAIT), Google Cloud (Adaptive Translation), arguably
  SYSTRAN (NFA, per reseller). Becoming table-stakes at the high
  end of the cohort.
- **Human verification in same SKU** — LILT alone (per ChapsVision
  cohort). Documented separately as a structural differentiator on
  the LILT page.
- **OCR bundled with MT** — SYSTRAN, Lingvanex. Worth checking
  before pairing an on-prem MT engine with a SaaS OCR — see
  [[../antipatterns/translation-procurement#Speech / OCR pre-processing breaks the air-gap]].

The number of `?` cells is the honest answer to "the source didn't
say." A `?` doesn't mean the engine *can't* do it — only that we
haven't ingested a source that confirms it. As future sources land,
matrix cells should move from `?` to ✓ or — with a citation.

## Pricing models surfaced by the source

Two access patterns, applicable to whichever engine the merchant picks
([source](https://transcy.io/blog/translation-engine-guide/)):

- **Bring-your-own-key (BYOK):** customer holds the engine vendor's
  API key, pays the engine vendor directly, integration platform
  charges nothing extra. Tone/parameter control usually exposed.
- **Pay-per-use through the platform:** flat $1 per 1000 words billed
  by the integration platform; no engine account needed; tone
  controls typically not exposed.

The BYOK / PPU split is a recurring shape across MT meta-platforms,
not unique to Transcy — worth recording as a pattern.

## Deployment as the threshold criterion

The ChapsVision 2026 review
([source](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/))
makes the strongest single argument for treating **deployment
architecture** as the *first* filter in enterprise MT procurement,
not the last:

> "On standard language pairs, translation quality is now broadly
> comparable across all seven solutions. Deployment architecture and
> compliance certifications are the real differentiators."

In other words: for HIPAA-covered entities, FedRAMP-required
agencies, defense contractors and other regulated buyers, a
cloud-only solution may **never** make it past procurement review
no matter how high the BLEU score
([source](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/)).
The source has an obvious conflict of interest (ChapsVision publishes
SYSTRAN and concludes by recommending it), but the threshold-criterion
framing matches Mordor MT's edge/on-prem 12.36% CAGR through 2031
([Mordor MT](https://www.mordorintelligence.com/industry-reports/machine-translation-market))
and the regulatory drivers in
[[../patterns/on-prem-translation]].

## On-prem / self-host short list

The most procurement-relevant filter for sovereignty-constrained
clients (and for [[../patterns/on-prem-translation|Build mode]]).
Updated to merge ChapsVision's 2026 cohort with Mordor's competitive
landscape:

| Engine | On-prem story | Caveat |
|---|---|---|
| Meta NLLB | Open weights, self-host | Low-resource quality weak (BLEU <20 many pairs) ([Mordor MT](https://www.mordorintelligence.com/industry-reports/machine-translation-market)) |
| OpenNMT, Marian, M2M100 | Open-source frameworks, self-host | Requires ML team to operate at production quality |
| Systran ([[../technologies/systran]]) | Pure Neural Server / translate Server (on-prem); private cloud + SaaS variants | Defense / regulated-industry default; 60+ languages, 150 pairs ([ChapsVision review](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/)) |
| RWS Language Weaver Edge ([[../technologies/language-weaver]]) | Edge deploys behind firewall, Kubernetes autoscaling | 3,500+ language combinations; bundles cleanly with RWS TMS ([ChapsVision review](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/)) |
| LILT ([[../technologies/lilt]]) | On-prem **and bare metal** for classified / air-gapped | Only cohort vendor with human verification in same SKU; FDA CFR Part 11 certified ([ChapsVision review](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/)) |
| AppTek ([[../technologies/apptek]]) | On-prem + cloud | Text + speech MT; low-resource language coverage strong ([AppTek](https://www.apptek.ai/technology/machine-translation)) |
| Omniscien Language Studio ([[../technologies/omniscien]]) | LSETS on-prem; Data Center Platform for billion-words/day scale | Hybrid NMT/SMT; unlimited-volume subscription pricing ([Omniscien LSETS](https://omniscien.com/products/language-studio/enterprise-translation-server/)) |
| Tilde MT ([[../technologies/tilde-mt]]) | Private cloud or on-prem | EU-vendor; 40+ engines + LLMs; Trados/MemoQ plugins ([Tilde](https://tilde.ai/translate/tilde-machine-translation/features/)) |
| Pangeanic ([[../technologies/pangeanic]]) | On-prem incl. air-gapped; task-specific SLMs for local infra | DAAIT real-time adaptive learning; EU-vendor ([Pangeanic](https://pangeanic.com/machine-translation)) |
| Lingvanex On-Premise | Vendor's primary positioning | 100+ languages; 20-year-encrypted perpetual-licence option ([Lingvanex on-prem](https://lingvanex.com/products/on-premise-machine-translation/)); independent benchmarks needed |
| DeepSeek (open weights) | Self-host viable | LLM-style translation, not dedicated MT |
| PROMT | On-prem available | Russia-based — sanctions risk |

DeepL Enterprise is **not** on this list — the ChapsVision review
explicitly classifies it as cloud-only
([source](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/)),
which contradicts the Transcy row's hint at a "DeepL On-Premise"
product. Verify with DeepL directly before recommending in either
direction.

All others in the candidate set above are SaaS-only or SaaS-default.

## What this comparison does not yet cover

Procurement-relevant dimensions still not addressed:

- **Quality benchmarks** — BLEU / COMET / human-eval scores per
  engine per language pair. Mordor cites BLEU >40 for major-pair NMT
  vs. 25-30 for statistical models, and BLEU <20 for NLLB on many
  low-resource pairs ([Mordor MT](https://www.mordorintelligence.com/industry-reports/machine-translation-market)),
  but no per-engine head-to-head data is in the sources.
- **Domain-specific quality** — legal, medical, financial. Mordor
  notes hybrid setups (NMT + terminology databases) cut post-editing
  ~30% in automotive and life sciences
  ([Mordor MT](https://www.mordorintelligence.com/industry-reports/machine-translation-market)),
  but no per-engine domain quality is broken out.
- **PII / data handling** — does the engine train on submitted
  content? Retention policies? Per-engine answers vary widely.
- **Throughput / SLA** — relevant for any enterprise procurement
  deliverable.
- **Cost at scale** — $1/1000-words PPU is convenient for small
  volumes but expensive at enterprise scale; BYOK pricing varies
  10x+ across engines.

## Open questions

- Independent benchmarks (academic or industry) comparing these
  engines on common test sets, especially for non-English-pair
  language directions.
- For EU-data-residency-constrained clients: which engines have a
  documented EU-only processing path? (DeepL clearly; Azure / Vertex
  via regional deploys; AWS via region selection.)
- DeepL's blind-test claim of beating ChatGPT-4, Google, Microsoft in
  July 2024
  ([Mordor TSM](https://www.mordorintelligence.com/industry-reports/translation-services-market))
  — independent verification would clarify the EU-pair quality
  ranking.
- Hardware footprint per on-prem engine at production volumes
  (covered as Open question on [[../patterns/on-prem-translation]]).

## Sources

- [Transcy Translation Engines_ Which One Best Suits You_](https://transcy.io/blog/translation-engine-guide/) — Transcy blog, vendor self-marketing, captured 2026-05-01. Establishes the original 8-engine candidate set; "best for X" claims unverified.
- [Machine Translation Market - Size, Companies & Share](https://www.mordorintelligence.com/industry-reports/machine-translation-market) — Mordor Intelligence MT market report; competitive-landscape section names additional engines beyond the Transcy list, plus quality and pricing context.
- [Translation Service Market Size, Drivers & Opportunities](https://www.mordorintelligence.com/industry-reports/translation-services-market) — Mordor Intelligence translation services market report; RWS Language Weaver positioning data and DeepL blind-test reference.
- [(11) Why You Should Choose an On-prem Translation System for Corporate Translation](https://www.linkedin.com/pulse/why-you-should-choose-on-prem-translation-system-corporate-5vksc/) — Lingvanex blog; Lingvanex On-Premise as a candidate engine.
- [Comparing Enterprise AI Translation Software in 2026_ Security, Deployment and Professional Accuracy, Comparing Enterprise AI Translation Software in 2026](https://www.chapsvision.com/blog/comparing-enterprise-ai-translation-software/) — ChapsVision blog reviewing 7 enterprise MT vendors (SYSTRAN, DeepL, RWS, LILT, Microsoft, Amazon, Google). Conflicted (ChapsVision publishes SYSTRAN) but provides verifiable deployment / certification structure; source of the "deployment as threshold criterion" framing.
- [Automated translation](https://website-translation.language-tools.ec.europa.eu/automated-translation_en) — European Commission WEB-T integration directory; eTranslation, ModernMT, Pangeanic, Tilde positioning for EU-language workflows.
