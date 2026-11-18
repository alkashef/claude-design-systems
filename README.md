# claude-design-systems

Design systems built with Claude. Each folder is one system, mirrored from the Claude Design System artifact of the same name. Each folder has its own `README.md`.

| Folder | What it holds |
| --- | --- |
| `presentation-editorial/` | Editorial system for 16:9 presentations: serif titles, hairlines instead of cards, one oxblood accent on paper. Tokens, 13 slide layouts (including bar, pie, line, scatter and table), guidelines, and a single-file HTML template. |
| `presentation-pixelated/` | Pixelated system for 16:9 presentations. It starts from `presentation-editorial/` and is being restyled. For now the folder holds its README only; the files follow once the restyle is mirrored. |

## Folder layout

A complete system folder has this structure:

- `README.md`: how to use the system and its visual rules.
- `tokens.json`: colors, type, spacing and radius.
- `components/`: one folder per slide layout, with guidelines and a live preview, plus `bundle.css`.
- `template/presentation-template.html`: the single-file deck template.

## Use

Open `<system>/template/presentation-template.html` in a browser. Press `E` to edit, `F` for full screen, `T` for the contents panel.

The repo copy of the template loads Instrument Serif and Instrument Sans from Google Fonts. The copy in the Claude artifact embeds the font files, so it also works offline.
