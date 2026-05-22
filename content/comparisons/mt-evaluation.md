---
type: comparison
tags:
  - topic/translation
  - mt
  - evaluation
  - benchmarks
sources:
  - 2022.amta-upg.4.Presentation
  - 2023.wmt-1.1
  - 2024.wmt-1.1
  - 2025.wmt-1.22
last_updated: 2026-05-23
---

# Machine translation evaluation

How MT systems are *actually* compared in 2026 — and why the answer
changed dramatically between 2022 and 2025. Procurement-relevant
because automatic-metric leaderboards (BLEU, COMET, MetricX) are
**known to be biased** at the top end, and yet most vendor pitches
still anchor on them.

For the engine catalog see [[mt-engines]]; for the why-deployment-
matters-more-than-quality framing see [[../patterns/on-prem-translation]].

## The two evaluation traditions

There are two communities running MT evaluations at scale, and they
disagree about what to measure:

- **Industry benchmark (Intento / e2f, AMTA 2022)** — commercial
  engines on commercial content (general, finance, hospitality,
  healthcare, legal, entertainment, education, IT, colloquial)
  across 11 language pairs. Methodology: rank engines by distance
  from a human reference translation; identify "best" cluster within
  an 83% confidence interval of the leader; report COMET as primary
  score
  ([Intento+e2f AMTA 2022](https://aclanthology.org/2022.amta-upg.4/)).
  500 segments per language-pair × industry-sector combination.
- **Academic benchmark (WMT, annually since 2006)** — research and
  commercial systems on test sets designed to avoid contamination
  (recent data, source-original translations, no MT post-editing in
  references). Domains shifted from news-only (pre-2022) to news +
  user-generated content + speech + literary + educational by 2025.
  Human evaluation is the gold standard; automatic metrics serve as
  signals for system selection but not final ranking
  ([WMT25](https://aclanthology.org/2025.wmt-1.22/)).

The academic benchmark caught up with industry reality late: WMT22
was still news-domain-only; WMT23 added 4 more domains; WMT24
introduced LLM baselines; WMT25 added difficulty sampling because
existing test sets had become too easy
([WMT25](https://aclanthology.org/2025.wmt-1.22/)).

## What metric to use, and why it keeps changing

The headline finding across both traditions: **automatic metrics are
biased**, and the bias *increases* as systems hill-climb on the
specific metric used for evaluation.

| Year | Primary metric | Method | Why |
|---|---|---|---|
| Pre-2018 | **BLEU** | n-gram precision against reference | Cheap, deterministic, language-agnostic. Notoriously weak correlation with human judgement at the top end |
| 2018–2022 | **BERTScore / TER / PRISM / hLEPOR** | Various automatic | Each captures a different signal; no single replacement for BLEU |
| 2022+ industry | **COMET** | Neural metric trained on human judgements | Intento picked COMET as the AMTA 2022 primary score "based on the high correlation with human judgement" ([Intento+e2f AMTA 2022](https://aclanthology.org/2022.amta-upg.4/)) |
| 2023 WMT | **DA+SQM** (Direct Assessment + Scalar Quality Metric) | Source-based human evaluation | Source-based (no reference contamination); professional annotators ([WMT23](https://aclanthology.org/2023.wmt-1.1/)) |
| 2024+ WMT | **ESA** (Error Span Annotation) | Annotators mark error spans then assign 0–100 segment score | "ESA produced 37% more clusters than DA+SQM while using only half the number of human annotations" ([WMT24](https://aclanthology.org/2024.wmt-1.1/)) — meaningfully more discriminative |
| 2025 WMT | **ESA + MQM** (Multidimensional Quality Metrics) | ESA for most pairs; MQM for English→Korean and Japanese→Chinese | MQM is more structured (error taxonomy) where ESA is more flexible ([WMT25](https://aclanthology.org/2025.wmt-1.22/)) |
| 2024–2025 supporting | **MetricX-23-XL** (Google) + **CometKiwi-DA-XL** (Unbabel) | Two distinct learned metrics, averaged → "AutoRank" | Used for *selecting* systems for human evaluation, not for final ranking ([WMT24](https://aclanthology.org/2024.wmt-1.1/)) |

The metric-bias trap is concrete: WMT24's top automatic-rank system
was **Unbabel-Tower70B**, but it didn't win the human evaluation.
The reason — Unbabel used COMET as its reward signal during
Minimum-Bayes-Risk decoding, so the model is hill-climbing on the
same metric that ranks it
([WMT24](https://aclanthology.org/2024.wmt-1.1/)). WMT25 hit the same
problem with **Shy-hunyuan-MT** topping automatic rankings on 15 of
16 language pairs but consistently losing human evaluation to
Gemini 2.5 Pro
([WMT25](https://aclanthology.org/2025.wmt-1.22/)).

**Procurement implication:** if a vendor anchors on "we lead on
COMET" or "we lead on MetricX," ask what their model was trained or
fine-tuned on. A vendor that uses metric X as a reward signal will
beat competitors on metric X without necessarily producing better
translations. See [[../antipatterns/translation-procurement#Procuring on automatic metric leaderboards]].

## The LLM era: 2023 → 2025 arc

The WMT findings papers across three years tell the headline story
of where MT actually stands, year by year.

**WMT23 — "LLMs Are Here But Not Quite There Yet"**
([WMT23](https://aclanthology.org/2023.wmt-1.1/)):

- GPT-4 (only 2 LLM submissions evaluated) was strong on UGC
  translation but **struggled** with speaker-gender translation and
  legal-domain text.
- Ranking from English into less-represented languages (Czech,
  Russian) was *lower* for GPT-4 than encoder-decoder systems —
  contradicting the "LLMs win everywhere" narrative.
- Human references **were not always best**: for Hebrew↔English,
  references appeared to be post-edited MT; for Chinese→English the
  human reference was *worse* than the majority of automatic
  translations.
- Manual evaluation results from DA+SQM and MQM yielded comparable
  cluster rankings — methodological convergence between the two
  protocols.

**WMT24 — "The LLM Era is Here but MT is Not Solved Yet"**
([WMT24](https://aclanthology.org/2024.wmt-1.1/)):

- Participation grew 50%; **most** participants used an LLM as part
  of their system, "generally by fine-tuning."
- Three top performers in three different categories:
  - Open + constrained: **IOL-Research** (wins 10 language pairs).
  - Participating system overall: **Unbabel-Tower70B** (wins 8).
  - Best system overall: **Claude 3.5 Sonnet** (wins 9 language
    pairs).
- English→Spanish was nearly flawless for the best systems — the
  language pair was effectively solved.
- Speech domain was the most challenging, "likely due to the ASR"
  noise polluting the source.
- Human references were in the winning cluster on 7 of 11 language
  pairs (i.e., for 4 pairs, the best MT was better than the human
  reference).
- 8 LLMs and 4 online translation providers added as organizer-
  contributed baselines alongside participant submissions.

**WMT25 — "Time to Stop Evaluating on Easy Test Sets"**
([WMT25](https://aclanthology.org/2025.wmt-1.22/)):

- 36 participant submissions + 24 LLM/commercial baselines = 60
  systems evaluated across 30 language pairs (16 with human eval).
- **Best system overall: Gemini 2.5 Pro** — top cluster in 14 of 16
  evaluated pairs.
- **Best constrained system: Shy-hunyuan-MT** — top cluster in 11
  pairs (but lost human eval to LLMs).
- Human references were in the winning cluster for only 6 of 15
  pairs — continuing the 2024 trend of "MT beats human references"
  on more pairs each year.
- Speech remained most challenging; **literary was *easiest*** (an
  inversion from prior years), likely because annotators score
  error-free literal translation high even when stylistic voice is
  lost.
- New innovation: **difficulty sampling** — using a regression-based
  difficulty estimator (`sentinel-src-25`) on candidate source
  documents to select the harder ones for the test set. The premise
  is that mainstream MT has improved enough that easy test sets no
  longer discriminate.
- New innovation: **document-level test sets** — sources provided as
  whole multi-paragraph documents, no sentence segmentation, letting
  participants choose their own translation granularity.
- Non-textual modalities: speech (audio + ASR transcript) and image
  (social-media screenshots) — first WMT iteration to include both.

### Where systems still fail (WMT25 test suites)

Six specialized test suites consistently surface remaining gaps
([WMT25](https://aclanthology.org/2025.wmt-1.22/)):

- **Gender choice / agreement** — systematic preference for masculine
  forms in Russian and Serbian; product-specific variation even
  among systems classified as balanced.
- **Robustness to non-standard input** — UGC with errors,
  code-switching, abbreviations still causes systematic semantic-
  role and named-entity errors.
- **Domain-specific terminology** — Icelandic EEA terminology and
  sports-specific Icelandic showed substantial difficulty in
  maintaining terminological consistency.
- **Legal-domain accuracy** — Gemini-2.5-Pro and Claude-4 are the
  clear leaders for English–Hindi legal translation; smaller open
  models lag substantially.
- **Linguistic complexity** — semantic roles, named entities,
  domain terminology, gender — all weak spots for SOTA in 2025.
- **Inclusivity** — improved markedly with advanced LLMs vs.
  previous years (a *positive* signal).

## Industry benchmark — Intento + e2f AMTA 2022

The reference industry benchmark for "which engine is best for which
domain"
([Intento+e2f AMTA 2022](https://aclanthology.org/2022.amta-upg.4/)).
Methodology and findings:

- **Coverage:** 31 commercial MT engines evaluated; 122,831 language
  pairs total across all engines (up from 99,760 a year prior, August
  2020 → August 2021). Niutrans (90K pairs), NLLB by Meta (38K),
  Alibaba (20K) the top breadth providers.
- **Test data:** 500 segments per (industry × language pair). 9
  industry sectors × 11 language pairs.
- **Industry sectors evaluated:** general, finance, hospitality,
  healthcare, legal, entertainment, education, IT, colloquial.
- **Ranking method:** distance-from-human-reference; "best" cluster
  defined as systems within 83% confidence interval of the leader,
  not a single winner.
- **Headline findings:**
  - 16 engines made the statistically-significant leader set across
    9 industries × 11 language pairs.
  - 6 engines provide minimal coverage across all 9 × 11 cells (2–4
    leader appearances each).
  - "Many engines perform best with English→Spanish and
    English→Chinese" — these are the *easy* directions.
  - **Legal, Financial, IT, and Healthcare** require careful vendor
    choice — relatively few engines reach the top cluster.
  - **Entertainment and Colloquial** show relatively low scores
    overall — customisation is the differentiator in these domains.
- **NLLB (open-source Meta):** mostly in the 2nd tier of commercial
  systems. On par with top tier for English→Spanish only. *Lower*
  than commercial for English→Chinese and English→Japanese.
  Best-in-class for English→Ukrainian/Arabic/Italian/Dutch/German/
  Korean/French at 3.3B parameters; English→Portuguese/Spanish at
  1.3B distilled.

The Intento+e2f benchmark is **commercial-shaped** (engines exist
and serve clients; industries match real procurement segments) where
WMT is **research-shaped** (system definitions are looser, human
references are the load-bearing comparator). Both are useful
references for procurement; neither is a substitute for the other.

## Open-source MT in benchmarks

NLLB's 2022 positioning ("2nd tier of commercial systems") is the
honest answer to the open-source-is-good-enough question
([Intento+e2f AMTA 2022](https://aclanthology.org/2022.amta-upg.4/),
[WMT25](https://aclanthology.org/2025.wmt-1.22/)).

WMT25 evaluated NLLB explicitly against participant systems and
commercial LLMs. Results:

- For low-resource pairs (English→Bhojpuri), **NLLB ranked 3rd
  overall** (after Algharb and human reference) on human eval,
  ahead of all other LLMs and participants. Open-source NLLB
  remained the strongest non-commercial option for very-low-resource
  pairs in 2025
  ([WMT25](https://aclanthology.org/2025.wmt-1.22/)).
- For mainstream pairs (English→Icelandic), NLLB scored 24.1 on
  human eval — well below the top cluster (87.5 for human, 63.2 for
  Shy-hunyuan-MT). NLLB has not closed the gap to commercial LLMs
  on better-resourced pairs.

**Build-mode implication:** for sovereign-deploy contexts where
NLLB self-host is the only option, the quality is *workable for
low-resource pairs* but degraded on mainstream ones (where
commercial LLM MT has improved fastest 2023–2025). Hybrid: NLLB
on-prem for sensitive low-resource workloads + cloud LLM MT for
non-sensitive high-resource workloads is the realistic shape if
quality is the binding constraint.

## What's still not measured well

Acknowledged limitations from the WMT25 paper
([WMT25](https://aclanthology.org/2025.wmt-1.22/)):

- **Document-level human evaluation** at scale — annotators see
  segments in context but score them individually. True
  document-level scoring (coherence, terminology consistency across
  document) is not in the WMT protocol yet.
- **Long-form content** — literary, multi-page legal contracts,
  full technical manuals. Test sets cap at ~9000 words per domain.
- **Multilingual / many-to-many** — WMT25 added a multilingual
  subtrack but only with automatic evaluation, not human.
- **Speech-to-speech translation** — WMT25 added audio as a source
  modality; speech-to-speech as the *output* is not in scope.
- **Domain-specific human eval** — most domains use general
  annotators. Legal/medical/financial domain-expert evaluation is
  a known gap.

## Open questions

- **Per-vendor benchmarks on the public WMT test sets** — most
  commercial vendors don't publish their own scores. Independent
  WMT organizers collect translations from "popular online providers"
  but identities are partially anonymized.
- **TTE (Time to Edit)** as a procurement metric — Translated's
  2026 positioning argues TTE is the right enterprise metric
  ([Translated 2026 assessment](https://translated.com/resources/machine-translation-2026-assessment)).
  Not measured in WMT or the AMTA 2022 study; an open methodology
  gap.
- **Quality on regulated-industry content** — Mordor MT cites BLEU
  >40 for major-pair NMT vs. 25–30 for statistical models
  ([Mordor MT](https://www.mordorintelligence.com/industry-reports/machine-translation-market)),
  but no per-engine per-regulated-domain benchmark exists in the
  sources captured here.

## Sources

- [2022.amta-upg.4.Presentation](https://aclanthology.org/2022.amta-upg.4/) — Intento + e2f joint study, AMTA 2022; 31 commercial MT engines × 9 industries × 11 language pairs; COMET as primary score; landscape and leader analysis.
- [2023.wmt-1.1](https://aclanthology.org/2023.wmt-1.1/) — WMT23 Findings paper; "LLMs Are Here But Not Quite There Yet"; first WMT with multi-domain test sets; DA+SQM protocol; English↔Hebrew added.
- [2024.wmt-1.1](https://aclanthology.org/2024.wmt-1.1/) — WMT24 Findings paper; "The LLM Era is Here but MT is Not Solved Yet"; ESA protocol introduced; AutoRank metric blend (MetricX + CometKiwi); Claude 3.5 Sonnet / IOL-Research / Unbabel-Tower70B as top performers.
- [2025.wmt-1.22](https://aclanthology.org/2025.wmt-1.22/) — WMT25 Findings paper; "Time to Stop Evaluating on Easy Test Sets"; difficulty sampling; document-level test sets; Gemini 2.5 Pro as overall leader; 60 systems × 30 language pairs.
