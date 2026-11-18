Use this system to build 16:9 technical presentations as one self-contained HTML file, in a terminal style: monospace titles, square marks, hairlines instead of cards, and one oxblood accent on a paper ground. Start from `template/presentation-template.html`. It holds twelve sample slides, a contents panel, a progress bar, full screen, an edit mode and print to PDF. Copy it, replace the sample text, and keep the layout classes.

## How to build a deck

- Copy `template/presentation-template.html`. Do not edit the `:root` token block, the font faces or the chrome CSS. Edit only the slides inside `#slides`, and set the deck name in `<title>`.
- Each slide is one `<section class="slide …">` of 1920 x 1080 px. Put the slides in the order you want. The contents panel and the progress bar read the slides, so they update by themselves.
- The contents label is the slide's `data-toc` value, else its first `h1` or `h2`. Add `data-group="Part name"` to a slide to start a new group in the panel. Each slide shows its number bottom right as `03/12`, except the opening title slide: numbering starts at 01 on the slide after it, and the contents panel uses the same numbers. The numbers update when you add, move or delete a slide.
- Pick a layout from `components/`: `TitleSlide`, `SectionSlide`, `BulletList`, `BulletImage`, `TwoColumnCards`, `ChartBar`, `ChartWaffle`, `ChartLine`, `ChartScatter`, `TableSlide`, `ReferencesSlide`, `StepSlide`. Copy its markup from `components/<Name>/preview.html`. The template has a sample of every layout except `StepSlide`.
- Press `E` in the browser to edit. Click any text and type. Use Duplicate slide, Delete slide and Save HTML in the top right. Save HTML downloads the finished file.
- Press `F` for full screen and arrow keys to move. Press `T` to fold the contents panel. Print to PDF gives one slide per page.

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
- **Text.** Set titles, column headings, the takeaway and the presenter name in `ink`. Everything inside a bullet is `text`, including point titles, bold lead-ins and links. Subtitles, role, date, table headers and the slide number are `grey`.
- **Accent.** `accent` (oxblood) is the only colour. Use it for the kicker, the section number, the `>` bullet marker, the step arrow, one key phrase in a takeaway, the 64px mark on a hairline, the progress fill and the current contents number. Never use it for body text or large areas.
- **Square everything.** `radius-none` is the only radius. Corners, bar ends, chart points, legend swatches, line joins and icon strokes are square. Do not draw circles, pills, rounded corners or round line caps, on slides or on the chrome.
- **Hairlines, not cards.** Separate content with 1px `line` rules: above a list, above two columns and between them, above the takeaway and above the byline. Do not use filled cards or shadows on slides. The presenter chrome alone uses `shadow-frame` and `shadow-popover`.
- **The signature.** The takeaway and the byline each sit under a hairline with a 3px `accent` mark, `accent-mark` long, on its left end. Use it only there.
- **Type.** Titles, labels and numbers are `JetBrains Mono`: `display` 96, `title` 72, `takeaway` 44, `chart-value` 24, `kicker` 20, `tick` 20, `number` 18. Reading text is `IBM Plex Sans`: `point-title` 34, `subtitle` 32, `content-subtitle` 32, `point-text` 30, `heading` 30, `body` 26, `byline` 24, `note` 22, `chart-label` 22, `caption` 20. The section number alone is `Jersey 25`, a pixel face: `stat` 200. Do not add sizes outside this scale. Do not set reading text in mono, and do not use the pixel face anywhere else.
- **Line length.** Mono letters are wide. One line holds 28 characters in `display`, 38 in `title` and 62 in `takeaway`. Shorten the words before you shrink the type.
- **Layout.** Every slide uses `margin-x` left and right, `margin-top` above and `margin-bottom` below, so every left edge sits at 160px. Content slides stack the title, the subtitle `space-55` below it, and the content `space-72` below that. Columns sit `space-64` either side of their dividing hairline.
- **Bullets.** Every list uses a `>` marker in `accent`, set in mono, in a `bullet-indent` gutter. One-line bullets sit `space-20` apart. Two-line points (title and sentence) sit `space-32` apart, with `space-6` between the title and its sentence.
- **Charts.** Each chart is a `<figure class="sl-chart" data-chart='…'>`. The template draws it as SVG from the JSON, so change the numbers there and reload. The types are `bar`, `waffle`, `line` and `scatter`. There is no pie: the waffle chart shows a split as 100 squares. Lines are stepped. Marks use `chart-1` to `chart-4` in that order, never cycled. The one series, bar or group the slide is about takes `chart-1` (oxblood); everything else takes `chart-muted` unless it needs its own identity. `chart-3` and `chart-4` are equally light, so colour never carries identity alone: two or more series always get a legend, lines also get end labels, and waffle parts fill in legend order. Text in charts uses text colours, never series colours: `chart-label`, `chart-value`, `tick` and `caption`. Mark sizes come from the chart tokens (`chart-bar-max`, `chart-line`, `chart-dot`, `chart-ring`, `chart-gap`); change a token and every chart follows. Use one y-axis only. Put `Source: …` in `caption` under every chart and table.
- **Tables.** Headers in `kicker` capitals, in `grey`, over a `line-strong` rule, rows split by `line` hairlines, names left, figures right in tabular numerals, and a total row in `tfoot` under an `ink` rule.
- **Images.** An image fills its frame edge to edge with no border. The empty frame shows `paper-deep` with a dashed `line-strong` border.
- **Motion.** Slides cross-fade in 220ms. The effect turns off for readers who ask for reduced motion. Add no other animation, and no blinking cursor.
- **Focus.** Controls show a 2px `accent` ring.

## Iconography

- The system uses no icons. A `>` marks a bullet, and the text `->` in `accent` joins the steps on the step layout. JetBrains Mono draws `->` as one arrow.
- No logo ships with this system. Set the presenter's organisation name in plain type on the title slide.
