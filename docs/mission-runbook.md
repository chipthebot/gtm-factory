# Mission Runbook

A mission is one sequential usecase hunt.

Default batch size is 32 prospects. Work in checkpoints of 8. After each
checkpoint, update the notes with what is working, what is slow, and whether
the next 8 should continue with the same search pattern.

## Before A Run

Create or verify:

- `prospect-index.local.csv`, copied from `templates/prospect-index.template.csv`
- `missions/<mission-slug>/README.md`
- `missions/<mission-slug>/PROMPT.md`
- `missions/<mission-slug>/leads.<batch-slug>.csv`
- `missions/<mission-slug>/notes.<batch-slug>.md`
- `missions/<mission-slug>/outputs/<batch-slug>/`

Read:

1. `AGENTS.md`
2. `docs/rules.md`
3. this runbook
4. `docs/cua-browser.md`
5. `docs/service-led-gtm.md`
6. the mission brief and prompt

## Batch Rule

- Default `{{COUNT}}` is 32.
- Run one browser-driven lane at a time.
- After every 8 prospects, write a checkpoint note.
- If packet quality is bad after the first 8, stop and change the search
  pattern before spending time on the remaining 24.
- Every reviewed prospect gets a row or a clear rejected note.

## Dedupe Rule

Append to `prospect-index.local.csv` as soon as a prospect is accepted. Do not
wait until the end of the run.

Use status values:

- `accepted`
- `rejected`
- `packet_drafted`
- `sent`
- `do_not_contact`

At the end of a batch, audit duplicates across the batch CSV, the local index,
older mission CSVs, and existing output folders. Do not delete duplicate rows
silently. Mark the weaker one and explain which row should win.

## Tool Fallback

Use the safest public path that gets the job done.

1. ComputerUserAgent / native Computer Use, when available.
2. Browser lane if Computer Use is not available.
3. Claude Code with `claude --chrome` for browser-heavy runs.
4. Local CUA CLI if the browser lane breaks.
5. Playwright for public pages and screenshots.
6. Web fetch/search for links, facts, and notes.

Never use logged-in, private, paywalled, or session-only pages as a workaround.
Record the mode used in the notes.

Suggested values:

- `browser_mode=computer_use`
- `browser_mode=browser`
- `browser_mode=claude_chrome`
- `browser_mode=cua_bypass`
- `browser_mode=playwright`
- `browser_mode=web_fetch_only`

Claude Code browser setup:

```sh
claude --chrome
```

Use this when a mission needs Chrome extension-backed browsing and native
Computer Use is not available.

Basic CUA checks:

```sh
cua list-apps
cua get-app-state com.google.Chrome.beta
cua restart-app com.google.Chrome.beta --url https://example.com --wait 90
```

If `cua` is missing, try the local fallback:

```sh
cd ~/Desktop/cua-bypass-kit
bin/cua list-apps
```

## Packet Shape

Each completed prospect should have:

```text
missions/<mission-slug>/outputs/<batch-slug>/<prospect-slug>/
|-- sources.md
|-- packet.md
|-- packet-meta.json
`-- assets/
    |-- source-map.md
    `-- missing-assets.txt
```

Save only useful public assets. Use lowercase kebab-case filenames:

- `homepage.png`
- `offer-page.png`
- `product-page.png`
- `service-page.png`
- `profile-page.png`
- `social-grid.png`
- `current-ads/meta-ad-01.png`
- `product-images/product-photo-01.png`
- `colors.txt`
- `fonts.txt`
- `missing-assets.txt`

If an asset is unavailable, say why. Use simple reasons:

- `not_found`
- `not_public`
- `login_required`
- `paywalled`
- `blocked_by_site`
- `rights_risk`
- `not_applicable`

## Creative Reviewer Pass

After the first research pass, spend a few more minutes looking for one useful
detail a human could naturally reference:

- a recent launch
- a strong quote
- a neglected case study
- a repeated review theme
- a buried product detail
- an old campaign worth reviving
- a visual gap
- a seasonal or time-sensitive signal

Then write:

- `lead_quality_grade`
- `lead_quality_score`
- `creative_reviewer_notes`
- `five_minute_find`
- `outreach_hook`

Do not confuse specific with invasive. Use public business or creator context,
not private life details.

## Done

Final notes should include:

- prospects reviewed
- A/B/C/D counts
- best 5 leads
- sendable packet count
- average minutes per prospect
- duplicates and rejected rows
- common source or tool failures
- whether to run another batch in this mission
