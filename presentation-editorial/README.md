Use this system to build 16:9 technical presentations as one self-contained HTML file, in an editorial style: serif titles, hairlines instead of cards, and one oxblood accent on a paper ground. Start from `template/presentation-template.html`. It holds twelve sample slides, a contents panel, a progress bar, full screen, an edit mode and print to PDF. Copy it, replace the sample text, and keep the layout classes.

## How to build a deck

- Copy `template/presentation-template.html`. Do not edit the `:root` token block, the font faces or the chrome CSS. Edit only the slides inside `#slides`.
- Each slide is one `<section class="slide …">` of 1920 x 1080 px. Put the slides in the order you want. The contents panel and the progress bar read the slides, so they update by themselves.
- The contents label is the slide's `data-toc` value, else its first `h1` or `h2`. Add `data-group="Part name"` to a slide to start a new group in the panel. Each slide shows its number bottom right, except the opening title slide: numbering starts at 1 on the slide after it, and the contents panel uses the same numbers. The numbers update when you add, move or delete a slide.
- Pick a layout from `components/`: `TitleSlide`, `SectionSlide`, `BulletList`, `BulletImage`, `TwoColumnCards`, `ChartBar`, `ChartPie`, `ChartLine`, `ChartScatter`, `TableSlide`, `ReferencesSlide`, `StepSlide`. Copy its markup from `components/<Name>/preview.html`.
- Press `E` in the browser to edit. Click any text and type. Use Duplicate slide, Delete slide and Save HTML in the top right. Save HTML downloads the finished file.
- Press `F` for full screen and arrow keys to move. Print to PDF gives one slide per page.

## Content fundamentals

- Write plain, short sentences. Use the active voice. Address the audience as "you" and the presenter as "I".
- Write one claim per slide title, in sentence case. "There is no magic" is a title. "Overview" is not.
- On every content slide, put a one-line subtitle under the title. Write the kicker, used only on the title and closing slides, as a label of two to six words. The stylesheet sets it in capitals.
- Start a bullet with a bold lead-in of one to four words, then one sentence of evidence.
- End a comparison with one takeaway line. Mark one key phrase in it.
- Do not use emoji, exclamation marks or marketing adjectives.
- Cite every external claim on a References slide, with a link for each source.

## Visual foundations

- **Ground.** Every slide sits on `paper`. The chrome stage behind the slide is `paper-deep`. There are no dark slides.
- **Text.** Set titles, column headings, the takeaway and the presenter name in `ink`. Everything inside a bullet is `text`, including point titles, bold lead-ins and links. Subtitles, role, date and the slide number are `grey`.
- **Accent.** `accent` (oxblood) is the only colour. Use it for the kicker, the section number, one key phrase in a takeaway, the 64px mark on a hairline, the progress fill and the current contents number. Never use it for body text or large areas.
- **Hairlines, not cards.** Separate content with 1px `line` rules: above a list, above two columns and between them, above the takeaway and above the byline. Do not use filled cards, shadows or rounded corners on slides. The presenter chrome alone uses `radius-sm`, `shadow-frame` and `shadow-popover`.
- **The signature.** The takeaway and the byline each sit under a hairline with a 3px `accent` mark, `accent-mark` long, on its left end. Use it only there.
- **Type.** Titles are `Instrument Serif`: `display` 128, `stat` 200 italic, `title` 88, `takeaway` 54 italic. Everything else is `Instrument Sans`: `subtitle` 32, `content-subtitle` 28, `heading` 30 semibold, `body` 26, `byline` 24, `kicker` 20, `note` 22, `number` 18. Do not add sizes outside this scale.
- **Layout.** Every slide uses `margin-x` left and right, `margin-top` above and `margin-bottom` below, so every left edge sits at 160px. Content slides stack the title, the subtitle `space-20` below it, and the content `space-72` below that. Columns sit `space-64` either side of their dividing hairline.
- **Bullets.** Every list uses a 16px `grey` dash in a `bullet-indent` gutter. One-line bullets sit `space-20` apart. Two-line points (title and sentence) sit `space-32` apart.
- **Charts.** Each chart is a `<figure class="sl-chart" data-chart='…'>`. The template draws it as SVG from the JSON, so change the numbers there and reload. Marks use `chart-1` to `chart-4` in that order, never cycled. The one series, bar or group the slide is about takes `chart-1` (oxblood); everything else takes `chart-muted` unless it needs its own identity. Two or more series always get a legend, and lines also get end labels, so colour never carries identity alone. Text in charts uses text colours, never series colours: `chart-label`, `chart-value` and `caption`, with `on-fill` only inside a fill. Mark sizes come from the chart tokens (`chart-bar-max`, `chart-bar-radius`, `chart-line`, `chart-dot`, `chart-ring`, `chart-gap`); change a token and every chart follows. Use one y-axis only. Put `Source: …` in `caption` under every chart and table.
- **Tables.** Headers in `caption` capitals over a `line-strong` rule, rows split by `line` hairlines, names left, figures right in tabular numerals, and a total row in `tfoot` under an `ink` rule.
- **Images.** An image fills its frame edge to edge with no border. The empty frame shows `paper-deep` with a dashed `line-strong` border.
- **Motion.** Slides cross-fade in 220ms. The effect turns off for readers who ask for reduced motion. Add no other animation.
- **Focus.** Controls show a 2px `accent` ring.

## Iconography

- The system uses no icons. A dash marks a bullet, and an arrow (→) in `accent` joins the steps on the step layout.
- No logo ships with this system. Set the presenter's organisation name in plain type on the title slide.
