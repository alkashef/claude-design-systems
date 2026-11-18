# claude-design-systems

Design systems built with Claude. Each folder is one system, mirrored from the Claude Design System artifact of the same name. Each folder has its own `README.md`, which is the brand book of that system.

| Folder | What it holds |
| --- | --- |
| `presentation-editorial/` | Editorial system for 16:9 presentations: serif titles, hairlines instead of cards, one oxblood accent on paper. Tokens, 12 slide layouts (including bar, pie, line, scatter and table), guidelines, and a single-file HTML template. |
| `presentation-pixelated/` | Terminal-style system for 16:9 presentations, built from the editorial one: monospace titles, square marks, one pixel-face section number, the same oxblood accent on paper. Tokens, 12 slide layouts (including bar, waffle, stepped line, scatter and table), guidelines, and a single-file HTML template. |

## Folder layout

Every system folder has the same structure:

- `README.md`: how to use the system and its visual rules.
- `tokens.json`: colours, type, spacing, radius, shadow and chart sizes.
- `components/`: one folder per slide layout, with guidelines (`README.md`) and a live preview (`preview.html`), plus `bundle.css` (the slide stylesheet) and `Cover/` (the cover of the system).
- `template/presentation-template.html`: the single-file deck template.

## Use

Open `<system>/template/presentation-template.html` in a browser. Press `E` to edit, `F` for full screen, `T` for the contents panel.

## Repo copy and Claude copy

The text files in a folder have the same content as in its Claude artifact. Two things differ:

- **Fonts.** The Claude artifact holds the font files (`fonts/*.woff2`), and its copy of the template embeds them, so that copy also works offline. The repo holds no font files. The repo copy of the template loads the same faces from Google Fonts, so it needs a network connection the first time.
- **Index.** The Claude artifact has one more file, `design-system.json`, which the Claude page uses as its index.
