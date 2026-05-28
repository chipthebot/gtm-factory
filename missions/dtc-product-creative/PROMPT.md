# Prompt - DTC Product Creative

Fill placeholders:

- `{{BATCH_LABEL}}`
- `{{BATCH_SLUG}}`
- `{{COUNT}}`
- `{{FOCUS}}`

## Mission

For `{{COUNT}}` DTC brands in `{{FOCUS}}`, build public research packets
with product creative opportunities and draft copy for human review.

Do not contact anyone. Do not generate media.

## Steps

1. Find brands through public sources: public ad libraries, TikTok, Instagram,
   Google Shopping, Shopify stores, category roundups, and marketplace pages.

2. Disqualify fast:
   - too large or too polished
   - no public hero product
   - no useful reviews, social, or ad surface
   - sensitive claims dominate the pitch

3. Collect:
   - brand name, site, product page
   - hero product, price if public, offer, bundles
   - paraphrased review themes and objections
   - current ad angles and missing angles
   - time-sensitive signal

4. Save source assets when appropriate:
   - `homepage.png`
   - `hero-product-page.png`
   - `product-images/`
   - `current-ads/`
   - `social-grid/`
   - `reviews.txt` with paraphrased themes only
   - `colors.txt`
   - `fonts.txt`

5. Audit 1 to 5:
   - product-page clarity
   - product photography
   - creator-style ad variety
   - hook variety
   - review mining
   - offer clarity
   - ad-to-page match

6. Write `packet.md` with 3 ad-angle directions, 1 creator-style storyboard,
   5 hooks, diagnosis, and risks.

7. Append a row to `leads.{{BATCH_SLUG}}.csv` and update
   `prospect-index.local.csv`.

## Done

- Rows and packets are source-backed.
- Reviews are paraphrased, not dumped.
- No media was generated.
- No outreach was sent.
