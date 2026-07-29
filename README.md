# saleshubpak-jobs

Scheduled jobs for [Sales Hub PK](https://saleshubpak.vercel.app), a deal
discovery app for Pakistani fashion brands.

This repository contains only automation:

- **`scrape.yml`** refreshes the product catalogue twice a day by running the
  scraper from the private application repository.
- **`warm.yml`** pings the public API every 5 minutes so the serverless
  functions stay warm and the CDN cache stays populated.

No application code and no user data live here.

## Configuration

Repository secrets required by the scrape job:

| Secret | Purpose |
|---|---|
| `PRIVATE_REPO_TOKEN` | Fine-grained PAT, read-only Contents, scoped to the app repo |
| `DATABASE_URL` | Pooled Postgres connection string |
| `DIRECT_URL` | Direct Postgres connection string |

Workflow logs in this repository are public. GitHub masks registered secret
values automatically, so credentials must always be supplied as secrets and
never printed.
