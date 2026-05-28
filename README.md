# GTM Factory

This is a generic shell for running mission-based GTM research.

A mission is a usecase hunt: pick one buyer or use case, find public signals,
build source-backed packets, and leave drafts for human review. This repo holds
the rules, prompts, schemas, and folder shape. It does not include
brand-specific campaigns, generated lead lists, or a website.

## What's Included

- `AGENTS.md` with the working rules for agents.
- `CLAUDE.md`, symlinked to `AGENTS.md`.
- `docs/` with sourcing rules, CUA browser notes, the mission runbook, and the
  service-led GTM frame.
- `templates/` with reusable packet, source, metadata, notes, and CSV schemas.
- `missions/_template/` for blank usecase hunts.
- example missions for language creators, DTC product creative, YouTube
  educators, B2B SaaS launch demos, podcast promo, and local service audits.

## Start Here

1. Read `AGENTS.md`.
2. Read `docs/rules.md`, `docs/mission-runbook.md`, and
   `docs/cua-browser.md`.
3. Copy `missions/_template/` to `missions/<mission-slug>/`.
4. Copy `templates/prospect-index.template.csv` to `prospect-index.local.csv`.
5. Fill in the mission brief and run prompt.

Generated CSVs, notes, screenshots, and packets are ignored by git by default.
Promote only the templates and instructions that should become part of the
repo.

## Create A Mission

```sh
cp -R missions/_template missions/my-mission
cp templates/prospect-index.template.csv prospect-index.local.csv
```

Then edit:

- `missions/my-mission/README.md`
- `missions/my-mission/PROMPT.md`
- `missions/my-mission/leads.template.csv`

Use `prompts/start-mission.md` when starting a fresh agent run.

## Customize A Mission

Missions are meant to be specific.

If a run needs logos, investors, pricing, ad screenshots, founder posts,
certifications, public contact routes, or anything else, add that requirement
to the mission itself:

- `README.md` explains why the field matters.
- `PROMPT.md` tells the agent how to find it and when to skip it.
- `leads.template.csv` adds the columns.
- `packet.md` and `sources.md` capture the evidence.
- `assets/source-map.md` maps saved files to public URLs.

Keep the repo-wide rules fixed: public sources only, cite URLs, no outreach,
no logged-in pages, and no invented claims. The mission decides what to
collect.

## Example Missions

- `language-learning-creators`
- `dtc-product-creative`
- `youtube-educator-packaging`
- `b2b-saas-launch-demos`
- `podcast-episode-promo`
- `local-service-creative-audit`

## Folder Shape

```text
gtm-factory/
|-- AGENTS.md
|-- CLAUDE.md -> AGENTS.md
|-- docs/
|   |-- rules.md
|   |-- mission-runbook.md
|   |-- cua-browser.md
|   `-- service-led-gtm.md
|-- prompts/
|   `-- start-mission.md
|-- templates/
|   |-- leads.template.csv
|   |-- packet.md
|   |-- packet-meta.json
|   |-- prospect-index.template.csv
|   |-- source-map.md
|   `-- sources.md
`-- missions/
    |-- README.md
    `-- _template/
        |-- README.md
        |-- PROMPT.md
        |-- leads.template.csv
        |-- notes.template.md
        `-- outputs/
```

## Definition Of Done

A mission run is done when it has:

- a deduped lead CSV
- source-backed packet folders for completed prospects
- local notes that explain what worked, what failed, and whether to continue
- no outreach sent by the agent
- no private, logged-in, paywalled, or session-only source material
