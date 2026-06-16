# Malaniru Marketing Site — GitHub Package

This folder is a self-contained static website, ready to push to a new GitHub repository and serve with GitHub Pages. Everything needed is inside this one folder — no build step, no dependencies, no separate CSS file (each page embeds its own styles).

## What's inside

16 HTML pages worked on 2026-06-16. `index.html` is the homepage (renamed from `ai-enablement.html`). Every internal link between these pages was updated to match.

| File | Role |
|---|---|
| `index.html` | Homepage / AI Enablement (was `ai-enablement.html`) |
| `ai-fluency.html` | AI Fluency path page |
| `building-sops.html` | Building SOPs path page |
| `foundations-ai-grant-management.html` | Grant management detail |
| `philanthropy-ai-adoption.html` | Adoption page |
| `philanthropy-ai-implementation-trends.html` | Implementation trends |
| `philanthropy-ai-research.html` | Research overview |
| `philanthropy-ai-support-gap.html` | Support gap page |
| `philanthropy-data-integrity-ip-security.html` | Data integrity / IP security |
| `philanthropy-data-security-compliance.html` | Data security / compliance |
| `philanthropy-digital-transformation.html` | Digital transformation |
| `policy-summary.html` | Policy summary |
| `questionnaires.html` | Questionnaires |
| `sources.html` | Sources / references |
| `workspace.html` | Workspace page |
| `coming-soon.html` | Placeholder page |

## How to deploy

See **`DEPLOY.md`** in this folder. It has two parts:

1. Commit this folder to a brand-new, empty GitHub repository.
2. Turn that repository into a live GitHub Pages site.

## Notes on what was and wasn't included

- **Only today's pages are here.** The older template pages (`about.html`, `blog.html`, `contact.html`, `services.html`, the original `index.html`, `newsletter.html`, `feed.html`) and the shared `style.css` were left out — none of the new pages link to them, and the new pages carry their own embedded CSS. If you want any of those legacy pages in the live site, copy them in and re-check links before deploying.
- **Comment-only references.** A handful of pages contain internal build-notes (inside `<!-- ... -->` comments) that still mention the old `ai-enablement.html` filename. These are not links and never render in the browser, so they were left as-is. Remove them later if you want a clean source.
