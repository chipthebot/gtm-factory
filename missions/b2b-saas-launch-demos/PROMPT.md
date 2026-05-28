# Prompt - B2B SaaS Launch Demos

Fill placeholders:

- `{{BATCH_LABEL}}`
- `{{BATCH_SLUG}}`
- `{{COUNT}}`
- `{{FOCUS}}`

## Mission

For `{{COUNT}}` B2B SaaS companies in `{{FOCUS}}`, build public research
packets with demo and launch-story directions for human review.

Do not contact anyone. Do not generate media.

## Steps

1. Find companies through public launch pages, Product Hunt, Launch YC,
   founder posts, changelogs, funding announcements, company blogs, and public
   review pages.

2. Disqualify fast:
   - mature company or obvious marketing team
   - no recent public signal
   - product cannot be understood without login
   - sensitive compliance or security claims dominate

3. Collect:
   - company name and website
   - category, target buyer, product promise
   - recent launch or changelog signal
   - founder post or public proof
   - demo assets and product screenshots
   - source URLs

4. Save source assets when appropriate:
   - `homepage.png`
   - `product-page.png`
   - `pricing-or-demo-page.png`
   - `launch-page.png`
   - `founder-posts/`
   - `product-screenshots/`
   - `social-cards/`
   - `colors.txt`
   - `fonts.txt`

5. Audit 1 to 5:
   - homepage clarity
   - visual demo clarity
   - buyer-specific story
   - founder-led content
   - launch assets
   - product screenshots
   - proof and claims discipline

6. Write `packet.md` with 3 launch/demo directions, 1 video or GIF
   storyboard, 5 founder-post/social hooks, diagnosis, and risks.

7. Append a row to `leads.{{BATCH_SLUG}}.csv` and update
   `prospect-index.local.csv`.

## Done

- Packets identify a real product story and demo angle.
- Claims are source-backed or flagged.
- No outreach was sent.
