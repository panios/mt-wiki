# MT Wiki

Research notes on machine translation engines, on-prem deployment, and enterprise procurement.

Browse the rendered wiki: **https://panios.github.io/mt-wiki/**

Curated by Panos Kostakos. Read-only — for questions or corrections, open an issue.

## What's here

- **`content/`** — the wiki content (markdown)
  - `comparisons/` — MT engines, translation platforms, market sizing
  - `technologies/` — vendor profiles (SYSTRAN, RWS Language Weaver, LILT, AppTek, Tilde MT, Omniscien, Pangeanic, Transcy)
  - `patterns/` — recurring architectural patterns (on-prem translation)
  - `antipatterns/` — translation procurement traps to avoid
- The rest is the [Quartz](https://quartz.jzhao.xyz/) static-site generator that builds the published site.

## How it's organised

Pages are tagged with `mode/build` (self-host / on-prem / sovereign deploy) and/or `mode/advise` (vendor evaluation / procurement). Most pages cross-link via Obsidian-style `[[wikilinks]]`, which render as proper links on the published site.

Citations are inline links to the original source (vendor blog, analyst report, etc.). Source captures themselves are not republished — only the synthesis.
