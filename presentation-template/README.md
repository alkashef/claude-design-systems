Use this system to build 16:9 technical presentations as one self-contained HTML file. Start from `template/presentation-template.html`. It holds seven sample slides, a contents panel, a progress bar, full screen, an edit mode and print to PDF. Copy it, replace the sample text, and keep the layout classes.

## How to build a deck

- Copy `template/presentation-template.html`. Do not edit the `:root` token block or the chrome CSS. Edit only the slides inside `#slides`.
- Each slide is one `<section class="slide …">` of 1920 x 1080 px. Put the slide in the order you want. The contents panel and the progress bar read the slides, so they update by themselves.
- The contents label is the slide's `data-toc` value, else its first `h1` or `h2`. The small line under it is the `sl-kicker` text. Add `data-group="Part name"` to a slide to start a new group in the panel.
- Pick a layout from `components/`: `TitleSlide`, `SectionSlide`, `NumberedRows`, `TwoColumnCards`, `StepSlide`. Copy its markup from `components/<Name>/preview.html`.
- Press `E` in the browser to edit. Click any text and type. Use Duplicate slide, Delete slide and Save HTML in the top right. Save HTML downloads the finished file.
- Press `F` for full screen, `T` for the contents panel, arrow keys to move. Print to PDF gives one slide per page.

## Content fundamentals

- Write plain, short sentences. Use the active voice. Address the audience as "you" and the presenter as "I".
- Write one claim per slide title, in sentence case. "There is no magic" is a title. "Overview" is not.
- Write the kicker as a label of two to six words. The stylesheet sets it in capitals. Do not type it in capitals.
- Start a bullet with a bold lead-in of one to four words, then one sentence of evidence.
- Do not use emoji, exclamation marks or marketing adjectives.
- Cite every external claim on a References slide. Number the sources and link each one.

## Visual foundations

- **Grounds.** Content slides sit on `cream`. Cards and rows sit on `paper` with a 1px `sand` border. Title, section and closing slides sit on `ink`. The chrome around the stage uses `deep` and `panel`. Never paint a slide with `deep` or `panel`.
- **Text.** Set titles and row titles in `ink`. Set body copy in `slate`. Set secondary row text in `muted`, only at 24px or larger. Set text on `ink` in `cream`, `mist` or `yolk`.
- **Accent.** `yolk` marks number badges, the progress fill, the primary button and the kicker on ink. `burnt` marks the kicker, links and one key phrase on cream. Never set `burnt` text on `ink`: it reads 2.7:1.
- **Tints.** `yolk-tint` (tool), `burnt-tint` (where AI helped) and `ink-tint` (review) fill note rows. Each carries an 8px left edge in `yolk`, `burnt` or `ink`. Text on a tint is `ink`.
- **Type.** Use `DM Sans` for all slide text and `JetBrains Mono` for code. Use the styles `display`, `title`, `subtitle`, `lead`, `card-title`, `row-title`, `body`, `row-text`, `kicker` and `note` at the sizes in tokens.json. Do not set body text below 22px.
- **Shape.** Round cards and rows with `radius-md`, notes with `radius-sm`, the header chip with `radius-chip`, badges and discs with `radius-pill`. Do not use shadows on slides.
- **Layout.** Content slides use `margin-x` left and right, `margin-top` above and `margin-bottom` below. Title, section and closing slides use `margin-cover`. Separate rows with `space-16` and the two cards with `space-40`.
- **Motion.** Slides cross-fade in 220ms. The effect turns off for readers who ask for reduced motion. Add no other animation.
- **Focus.** Controls show a 3px `yolk` ring. It reads 8:1 on `deep` and `panel`.

## Iconography

- Use 24px line icons drawn inline as SVG. Set `stroke-width` to 1.8, round caps and joins, no fill.
- Draw the icon in `sand-deep` beside a note row. It is decoration. The words carry the meaning.
- Use the arrow shape from `StepSlide` (`sl-arrow`, in `burnt`) to join steps. Do not use emoji or icon fonts.
- No logo ships with this system. Set the presenter's own organisation name in plain `DM Sans` on the title slide.
