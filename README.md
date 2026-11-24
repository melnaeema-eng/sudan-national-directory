# Sudan National Directory — دليل السودان الشامل

Standalone bilingual-ready directory project for Sudan, hosted as a static site on Cloudflare Pages.

## Deployment
- GitHub repository: `melnaeema-eng/sudan-national-directory`
- Cloudflare Pages: connect this repository, production branch `main`
- Framework preset: None
- Build command: leave empty
- Output directory: `/` (repository root; if Cloudflare requires an output path, use `.`)
- Proposed hostname: `directory.basmat-alnawabig.com.sa` (verify DNS/domain before configuration)

## Database
Uses the existing Supabase project **sudanese-restaurant**, but only isolated tables:
- `public.sd_categories`
- `public.sd_listings`

Existing restaurant tables are left unchanged. RLS only permits public reads of published listings. The web app includes a public Supabase publishable key, **not** a secret/service-role key.

## Current state
12 directory categories initialized; no real listings have been imported yet. Search/filter UX works for public records after verification and publication. Current client loads up to 1,000 newest published records; pagination/server-side search is required before scaling beyond that.

## Data quality
Never mark a record verified without supporting source or direct confirmation. Maintain a record's address precision, verification level, operating status, sources, and timestamp. Do not publish sensitive infrastructure locations or personal contact details without authorization.
