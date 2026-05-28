# Prompt - Podcast Episode Promo

Fill placeholders:

- `{{CATEGORY}}`
- `{{CATEGORY_SLUG}}`
- `{{COUNT}}`

## Mission

For `{{COUNT}}` podcast hosts in `{{CATEGORY}}`, build public research packets
with episode-promo directions for human review.

Do not contact anyone. Do not download full audio or video. Do not generate
media.

## Steps

1. Find shows through Apple Podcasts, Spotify public pages, YouTube, podcast
   websites, LinkedIn, X, Instagram, and public podcast directories.

2. Disqualify fast:
   - network-backed or professionally packaged show
   - no recent episode
   - no public contact route
   - no public episode, YouTube, or social surface

3. Collect:
   - show name, host, site, Apple/Spotify/YouTube URLs
   - public contact route
   - category, audience, recent episode, guest/topic
   - current clip, audiogram, quote-card, and social patterns
   - sponsor or launch signal if public

4. Save source assets when appropriate:
   - `show-art.png`
   - `homepage.png`
   - `recent-episode-page.png`
   - `youtube-channel.png`
   - `social-grid/`
   - `episode-stills/`
   - `guest-links.txt`
   - `colors.txt`
   - `fonts.txt`

5. Audit 1 to 5:
   - show art clarity
   - episode page quality
   - clip strategy
   - YouTube thumbnail quality
   - guest-share usefulness
   - social cadence
   - sponsor/read integration

6. Write `packet.md` with 3 promo-pack directions, 1 clip/audiogram
   storyboard, 5 hooks, diagnosis, and risks.

7. Append a row to `leads.{{CATEGORY_SLUG}}.csv` and update
   `prospect-index.local.csv`.

## Done

- Packet is tied to one real recent episode.
- It does not imply guest endorsement.
- No outreach was sent.
