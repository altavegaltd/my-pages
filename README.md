# my-pages

Personal hub of HTML tools built with Claude, hosted on Cloudflare Pages.

## Structure

```
/
├── index.html       ← landing page (card grid)
├── tools.json       ← manifest of tools — edit this to add/remove cards
├── tools/           ← individual HTML tools
│   └── prompt-builder.html
└── README.md
```

## Publishing a new tool (with GitHub Desktop)

1. Claude will give you two things each session:
   - a new `.html` file for the tool
   - an updated `tools.json` with a new entry
2. Drop the `.html` into `my-pages/tools/`.
3. Replace `tools.json` at the root.
4. Open **GitHub Desktop** — it'll show both changes.
5. Write a short commit message like `Add <tool-name>` and click **Commit to main**, then **Push origin**.
6. Cloudflare Pages auto-deploys in ~30 seconds.

## Updating an existing tool

Same flow — just replace the file in `tools/` and commit via GitHub Desktop. No need to edit `tools.json` unless the title/description/tags changed.

## Removing a tool

Delete the file from `tools/` and remove its entry from `tools.json`.

## Adding a tool manually

`tools.json` shape:

```json
{
  "id": "unique-slug",
  "title": "Name shown on the card",
  "description": "One-sentence description.",
  "path": "tools/filename.html",
  "emoji": "✍️",
  "tags": ["work", "marketing"],
  "added": "YYYY-MM-DD"
}
```

Tags drive the filter chips on the landing page — keep them consistent (`work`, `personal`, `marketing`, `planning`, `writing`, etc.).
