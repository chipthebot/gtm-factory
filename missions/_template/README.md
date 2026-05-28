# Mission - <Segment Or Usecase>

## Mission

Find source-backed prospects or usecases in `<segment>` where `<finished outcome>` would be useful.

## Hypothesis

This segment is worth testing because:

- public signal:
- clear buyer or user:
- repeatable first deliverable:
- likely budget or urgency:

## Fit Signals

Strong prospects show:

- signal 1
- signal 2
- signal 3

## Reject Fast

Skip prospects when:

- the usecase is unclear
- public evidence is too thin
- the work would depend on private or logged-in data
- the claims would require legal, medical, financial, security, or compliance review
- there is no stable dedupe key

## Output

Use:

```text
missions/<mission-slug>/outputs/<batch-slug>/<prospect-slug>/
|-- sources.md
|-- packet.md
|-- packet-meta.json
`-- assets/
    |-- source-map.md
    `-- missing-assets.txt
```

## Done

The batch is done when the CSV, source notes, packets, and final notes are complete, or when the stop reason is written clearly.
