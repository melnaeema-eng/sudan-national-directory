# Sudan National Directory — دليل السودان الشامل

Bilingual (Arabic-first and English) public directory for businesses, health facilities, schools, restaurants, and public services across Sudan. The site is a static Cloudflare Pages app backed by the isolated `sd_*` tables in the existing Supabase project.

## Deployment

- GitHub repository: `melnaeema-eng/sudan-national-directory`
- Production branch: `main`
- Static site output: repository root (no build command)
- Public site: [directory.basmat-alnawabig.com.sa](https://directory.basmat-alnawabig.com.sa/)
- Reviewer dashboard: `/admin.html`

## Database and publication

The site uses the existing Supabase project `sudanese-restaurant`, with separate directory tables:

- `public.sd_categories`
- `public.sd_listings`
- `public.sd_listing_suggestions`
- `public.sd_directory_admins`

Public visitors can read published records and submit new or corrected information. Suggestions remain private and pending until an authorized reviewer checks the source and approves them. Approval publishes the record; rejection keeps it out of public search. Reviewer access is allowlisted in the database and uses Supabase email sign-in. No service-role key is present in the website.

## Data snapshot (26 November 2026)

- 13 directory categories.
- 253 published listings: 195 health listings plus 58 restaurants and cafés across Port Sudan, Kassala, Wad Madani, Omdurman, and Nyala.
- 105 suggestions remain pending: bank branches, health-facility leads, and temporary university admissions centers.
- Seasonal admissions centers must be checked for dates and should not be represented as permanent university locations.
- Phone, WhatsApp, opening hours, operating status, address, and map links are shown when provided. Missing values remain blank or unconfirmed instead of being invented.

These counts are a snapshot and will change as submissions are reviewed and more cities are added.

## Photos and data quality

Contributors can propose a photo by URL or upload a JPEG, PNG, or WebP file (up to 5 MB). They must confirm they have permission to publish it and provide credit/source details. Photos stay out of the public directory until review. Do not copy or scrape user photos from Google Maps; use photos with permission or a suitable license.

Do not mark a facility as open based only on a directory listing. The reviewer records source review separately from operating status. Record a source URL or explain direct confirmation in the reviewer note. Preserve the distinction between a verified information source and an unconfirmed opening status.

Existing restaurant tables and data are untouched. The client uses a publishable Supabase key only; public writes are restricted to pending suggestions, while reviewer publishing uses an authorization-checked database function.
