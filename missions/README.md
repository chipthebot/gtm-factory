# Missions

Each folder here is one mission.

A mission is a usecase hunt with one target buyer or use case, one source
pattern, one packet shape, and one batch of prospects.

Start by copying `_template/`:

```sh
cp -R missions/_template missions/<mission-slug>
```

Then fill in:

- `README.md`
- `PROMPT.md`
- `leads.template.csv`

## Example Missions

- `language-learning-creators` - creator-resource hunts for study decks,
  transcripts, vocabulary packs, and repeat-review products.
- `dtc-product-creative` - product-page, review, ad, and social research for
  DTC creative packets.
- `youtube-educator-packaging` - thumbnail, title, shorts, and channel
  packaging packets for educational creators.
- `b2b-saas-launch-demos` - launch, changelog, founder-post, and demo-story
  packets for early B2B SaaS teams.
- `podcast-episode-promo` - episode-specific promo, quote-card, clip, and
  guest-share packets.
- `local-service-creative-audit` - public proof, service-page, review, and
  local creative audits.

Generated files stay local by default:

- `leads.<batch-slug>.csv`
- `notes.<batch-slug>.md`
- `outputs/<batch-slug>/`
