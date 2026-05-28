# Prompt - Local Service Creative Audit

Fill placeholders:

- `{{SERVICE_CATEGORY}}`
- `{{METRO}}`
- `{{METRO_SLUG}}`
- `{{COUNT}}`

## Mission

For `{{COUNT}}` local service businesses in `{{SERVICE_CATEGORY}}` around
`{{METRO}}`, build public creative-audit packets for human review.

Do not contact anyone. Do not generate media.

## Steps

1. Find businesses through Google Maps, public business profiles, local
   directories, review sites, company websites, Facebook, Instagram, and public
   ad libraries.

2. Disqualify fast:
   - national chain or obvious agency-backed brand
   - too few public reviews
   - no public website or profile
   - no useful job, service, review, or social material
   - privacy or regulated-service risk is high

3. Collect:
   - business name, service area, website, business profile
   - public contact route
   - main services
   - visible proof: reviews, certifications, job photos, case studies
   - social and ad activity if public
   - time-sensitive local or seasonal signal if relevant

4. Save source assets when appropriate:
   - `logo.png`
   - `homepage.png`
   - `business-profile.png`
   - `service-page.png`
   - `current-ads/`
   - `portfolio/`
   - `latest-social/`
   - `colors.txt`
   - `fonts.txt`

5. Audit 1 to 5:
   - website quality
   - proof visibility
   - photography quality
   - review responsiveness
   - service clarity
   - social cadence
   - ad presence

6. Write `packet.md` with 3 content/ad directions, 1 short-form concept, 5
   hooks, diagnosis, and privacy or rights risks.

7. Append a row to `leads.{{METRO_SLUG}}.csv` and update
   `prospect-index.local.csv`.

## Done

- Packet uses public business context only.
- No personal or customer-sensitive details are used.
- No outreach was sent.
