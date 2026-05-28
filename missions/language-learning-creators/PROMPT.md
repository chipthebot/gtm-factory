# Prompt - Language Learning Creators

Fill placeholders:

- `{{BATCH_SLUG}}`
- `{{COUNT}}`
- `{{FOCUS}}`

Before starting, read:

1. `AGENTS.md`
2. `docs/rules.md`
3. `docs/mission-runbook.md`
4. `missions/language-learning-creators/README.md`

## Mission

For `{{COUNT}}` language-learning creators in `{{FOCUS}}`, build a public,
deduped list and, when useful, priority packets for human review.

Do not contact anyone.

## Steps

1. Check duplicates in `prospect-index.local.csv`, existing mission CSVs, and
   `outputs/`.

2. Find creator-led prospects through public sources: YouTube, Instagram,
   TikTok, creator websites, course pages, link-in-bio pages, memberships,
   Patreon, podcasts, books, app pages, and public shops.

3. Disqualify fast:
   - no clear language-learning audience
   - no public resource, course, transcript, vocabulary, worksheet, or deck
   - no stable public profile or dedupe key
   - private, paid, or login-only source material is required
   - risky claims dominate the pitch

4. Collect:
   - creator name
   - primary language or niche
   - stable dedupe key
   - primary profile and website
   - audience signal
   - paid or owned resource signal
   - repeat-review or flashcard signal
   - concrete study artifact idea
   - source URLs
   - risk flags

5. Grade each lead:
   - `A`: strong audience plus clear resource fit
   - `B`: promising, but one key piece needs verification
   - `C`: useful for learning, not priority human review
   - `D`: weak or risky fit

6. Append rows to `leads.{{BATCH_SLUG}}.csv`.

7. For priority prospects, create:

```text
missions/language-learning-creators/outputs/{{BATCH_SLUG}}/<creator-slug>/
|-- sources.md
|-- packet.md
|-- packet-meta.json
`-- assets/
    `-- source-map.md
```

8. Write `notes.{{BATCH_SLUG}}.md` with best leads, duplicate audit, weak
   evidence, and next-run recommendation.

## Done

- CSV has no duplicate dedupe keys.
- Every row has public source URLs and collection date.
- Priority packets explain permissions and risk.
- No outreach was sent.
