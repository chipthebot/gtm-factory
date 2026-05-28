# Prompt - [Mission Name]

Fill placeholders:

- `{{BATCH_LABEL}}`
- `{{BATCH_SLUG}}`
- `{{COUNT}}`
- `{{FOCUS}}`

Before starting, read:

1. `AGENTS.md`
2. `docs/rules.md`
3. `docs/mission-runbook.md`
4. `docs/service-led-gtm.md`
5. `missions/[mission-slug]/README.md`

## Mission

For `{{COUNT}}` prospects in `{{FOCUS}}`, build public research packets for
human review.

Do not contact anyone.

## Steps

1. Check for duplicates in `prospect-index.local.csv`, current mission CSVs,
   and existing `outputs/`.

2. Find prospects through public sources:
   websites, public profiles, launches, directories, marketplaces, blogs,
   social profiles, public ads libraries, review pages, and other relevant
   primary sources.

3. Disqualify fast:
   - no clear fit
   - no stable public dedupe key
   - no usable source material
   - login, paywall, or gated flow required
   - sensitive or risky claims dominate the pitch

4. Collect:
   - prospect name
   - entity type
   - stable dedupe key
   - website or primary profile
   - public contact route if visible
   - target buyer or use case
   - current public signal
   - useful public assets
   - source URLs
   - risk flags

5. Create a packet folder:

```text
missions/[mission-slug]/outputs/{{BATCH_SLUG}}/<prospect-slug>/
|-- sources.md
|-- packet.md
|-- packet-meta.json
`-- assets/
    |-- source-map.md
    `-- missing-assets.txt
```

6. Write `packet.md`:
   - why this might fit
   - public signal
   - 2-3 sentence diagnosis
   - 3 concrete directions
   - draft email and DM for human review, if useful
   - risks and claims to verify

7. Append a row to `leads.{{BATCH_SLUG}}.csv`.

8. Update `prospect-index.local.csv`.

9. After every 8 prospects, update `notes.{{BATCH_SLUG}}.md`.

## Done

- CSV rows are deduped.
- Every completed packet cites public sources.
- Notes explain quality, failures, duplicates, and whether to continue.
- No outreach was sent.
