# Sykon AI Labs

The private panel where every AI initiative at **Sykon Properties** lives — solutions, presentations and essential references, under one address.

**Live site:** deployed to GitHub Pages from `main` (see `.github/workflows/pages.yml`).

## Structure

| Path | Purpose |
|---|---|
| `index.html` | The entire site — design, solution cards and links directory are authored here. |
| `data/config.json` | Site configuration. Set `presentationsVaultUrl` to the Zoho WorkDrive share link of the presentations folder. |
| `data/presentations.json` | The presentation shelf. Updated automatically every Monday 11:00 GST by the sync routine; can also be edited by hand. |
| `assets/` | Favicon and brand assets. |

## The Monday sync

A scheduled routine runs **every Monday at 11:00 Gulf Standard Time (07:00 UTC)**. It:

1. Reads `data/config.json` → `presentationsVaultUrl` (the Zoho WorkDrive folder).
2. Looks for presentations newer than the newest entry in `data/presentations.json`.
3. Appends them as `{ "title", "date" (YYYY-MM-DD), "description", "link" }` — titles, dates and links only; no confidential content is copied into this public repository.
4. Commits the updated JSON, which redeploys the site.

Until `presentationsVaultUrl` is set, the routine exits without changes and the site shows the vault as *pending connection*.

## Adding a solution card

Edit the `SOLUTIONS` array near the bottom of `index.html` — each card takes an index, tag, title, status (`Live` / `In Development` / `Planned`), a one-line description and an optional link.

## Confidentiality

This repository is public. Keep it to **titles, descriptions and access-controlled links only** — never commit presentation files, client data, credentials or internal documents.
