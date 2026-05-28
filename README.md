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
- `docs/example-packet/` with a synthetic completed packet.
- `templates/` with reusable packet, source, metadata, notes, and CSV schemas.
- `missions/_template/` for blank usecase hunts.
- example missions for language creators, DTC product creative, YouTube
  educators, B2B SaaS launch demos, podcast promo, and local service audits.

## Start Here

1. Read `AGENTS.md`.
2. Read `docs/rules.md`, `docs/mission-runbook.md`, and
   `docs/cua-browser.md`.
3. Copy `missions/_template/` to `missions/<mission-slug>/`.
4. Create `prospect-index.local.csv` from the template if it does not exist.
5. Fill in the mission brief and run prompt.

Generated CSVs, notes, screenshots, and packets are ignored by git by default.
Promote only the templates and instructions that should become part of the
repo.

## Share This Repo

This repo is public:

```text
https://github.com/chipthebot/gtm-factory
```

Friends can clone it, fork it, or copy a mission folder into their own repo.

```sh
git clone https://github.com/chipthebot/gtm-factory.git
cd gtm-factory
```

The repo is designed to work when a fresh agent opens it. Give the agent this:

```text
Read README.md, AGENTS.md, docs/rules.md, and docs/mission-runbook.md.
Then help me create or run a mission.
Use public sources only. Do not contact prospects.
```

Local research outputs are ignored by git, so a friend can run missions without
accidentally committing lead lists, screenshots, or packets.

## Create A Mission

```sh
cp -R missions/_template missions/my-mission
test -f prospect-index.local.csv || cp templates/prospect-index.template.csv prospect-index.local.csv
```

Then edit:

- `missions/my-mission/README.md`
- `missions/my-mission/PROMPT.md`
- `missions/my-mission/leads.template.csv`

Use `prompts/start-mission.md` when starting a fresh agent run.

## Run A Batch

Use one naming pattern everywhere:

- `MISSION_SLUG`: `my-mission`
- `BATCH_LABEL`: `Example segment`
- `BATCH_SLUG`: `example-segment`
- `COUNT`: `8`, `16`, or `32`
- `FOCUS`: the market, buyer, or use case

Set up local files:

```sh
cd missions/my-mission
cp leads.template.csv leads.example-segment.csv
cp notes.template.md notes.example-segment.md
mkdir -p outputs/example-segment
```

Delete the synthetic sample row from `prospect-index.local.csv` and from the
new batch CSV before a real run.

For each completed prospect, create:

```text
missions/my-mission/outputs/example-segment/<prospect-slug>/
|-- sources.md
|-- packet.md
|-- packet-meta.json
`-- assets/
    |-- source-map.md
    `-- missing-assets.txt
```

Use the shared files in `templates/` as the starting point for those packet
files.

## Which Prompt Does What

`missions/<mission-slug>/PROMPT.md` is the mission brief. It tells the agent
what to find, what to skip, and what fields matter.

`prompts/start-mission.md` is the wrapper prompt. Paste it into a fresh agent
thread after filling in the mission and batch names.

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

Contact routes, possible angles, and draft copy are local artifacts for human
review. Agents must not send them.

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
|   |-- example-packet/
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
