# Pk-in--black — Content HQ

Git-as-CMS. The repo is the source of truth for every piece of content from idea to publish.

## Folder map

| Folder        | What lives here                                                      |
| ------------- | -------------------------------------------------------------------- |
| `/ideas`      | Raw captures — one `.md` per idea, no structure required             |
| `/research`   | Sourced notes, links, quotes, stats. One file per slug               |
| `/drafts`     | Working pieces with front-matter. Iterate here                       |
| `/ready`      | Approved, ready to publish. Nothing else changes after this point    |
| `/published`  | Archive. Front-matter updated with publish date + live URL           |
| `/assets`     | Images, thumbnails, audio, video. Upload from iPad or generate       |

## The loop

1. **Capture** — drop the idea in chat. I save it to `/ideas/<slug>.md`.
2. **Research** — I web-search and write sourced notes into `/research/<slug>.md`.
3. **Draft** — I write `/drafts/<slug>.md` from `TEMPLATE.md`.
4. **Review** — read on iPad. Comment in chat or via PR review. I revise.
5. **Approve** — file moves from `/drafts` to `/ready`.
6. **Publish** — copy from `/ready` into the platform (Substack, X, LinkedIn, etc.).
7. **Log** — move to `/published`, fill in `published_at` and `url` in front-matter.

## Cadence

`schedule.md` at the repo root tracks the weekly plan. I roll it forward each Monday.

## Upgrade points

- **fal.ai / Replicate MCP** — auto-generate thumbnails into `/assets`
- **Notion MCP** — swap `/drafts` for a kanban board if files get heavy
- **Zapier MCP** — auto-publish from `/ready` to platforms
