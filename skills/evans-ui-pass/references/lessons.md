# Lessons

Raw nudges from design iteration tasks, dated. A lesson graduates into
SKILL.md when Evan repeats it or it decides an outcome.

## Saturday, November 21, 2026 — Flight Watches (space, built and iterated same day)

- "Did you run emil's?" / "Did you run better-ui on it?" — both had only
  been briefed as principles. Evan's fix: install the actual skills
  (vendored, byte-identical) and run them. Origin of the "real skills"
  rule.
- Frosted glass over a sky, Hedvig Letters Serif, and a micro-illustration
  treatment were picked from his Tidbits and applied by name.
- "Can you make it light/dark respect the system?" — no toggle.
- "Lol those clouds" — the CSS-drawn clouds failed. Real Pexels photos
  replaced them: Pixabay's sea of clouds for light, Francesco Ungaro's
  twilight cloudscape for dark. Judged from the frames, not the listings.
- "Remove the halftone grain" — grain overlay cut entirely.
- "Remove the random colored glows, that looks slop-y" — per-route glows
  cut entirely.
- "The row of pills at the top just screams slops" — top controls went
  quiet and small-radius; then the pill row itself was removed: totals
  became badges next to the header, "last updated" moved to a footer.
- "Much better visual hierarchy... as well as better use of color
  language" — hierarchy and semantic color became standing rules, and
  the whole better-* family ran again after the changes.
- better-colors measured light dim text at 2.66:1 over the sky and dark
  faint text at 3.16:1 on glass. Both looked fine. Measure, do not
  estimate.
- The audit browser rendered only the light scheme; dark was verified
  from source values and contrast math. Reported as not seen, in those
  words.
- The Denver detail page explained "Delta is against the current lowest
  option" on a watch whose only option was JetBlue — "Delta" was the
  math term. Copy fixed to "Differences are measured against the current
  lowest option in this watch." Origin of the domain-noun collision rule.
- "Add a light screen, really subtle to the background but just to
  increase contrast" — a faint screen layer went over the background
  photo in both schemes (white wash in light, dark veil in dark), above
  the scrim, to even out the photo's bright and dark patches so text
  contrast holds across the whole page, not just on average.
- "Also pick an artsier background / More like my design tidbits" —
  the cloud photos were re-rendered as dithered halftones of
  themselves (blue/white duotone in light, silver dots over near-black
  in dark), straight from the morrre_dsgn Tidbits reference he filed
  two days earlier. This rewrote rule 4: the ban is on grain overlays
  laid over a finished design; a photograph dithered as itself is a
  named treatment.
- The first halftone cut failed in Evan's hands: "Can't see anything
  now the contrast is really bad," then "It's too busy I think." The
  fix that held: calm the backdrop itself (ink pulled close to the
  paper colour, tonal range compressed, finer softened dots —
  near-flat at a glance, dither visible only up close) and move the
  separation to the content side (panes went from 30% to 86–94%
  opacity, heavier scrim and screen, text halos). Contrast was
  measured by compositing the real backdrop pixels under the layers:
  all pairs ≥4.5:1, body text 13–16:1. Lessons: fix a busy backdrop in
  the backdrop first, and measure contrast over a patterned image on
  its actual pixels, never by reasoning.
- "Also a Y-axes should start at 0" — the price trend chart auto-scaled
  its Y axis to the data range, so a few hundred dollars of fare
  movement filled the whole chart and read as a swing. Domain set to
  start at 0. Stated as a general rule, so it graduated into rule 7 the
  same day: chart axes do not exaggerate.
- "Include a button to proactive launch a refresh" — the standing
  daily check got a manual trigger in the header: same check, a
  visible checking state, and the list refetches itself when the new
  prices land. Automation does not remove the on-demand path.
- "Remove the 'new watch' flow, I'll only ever ask you to put in
  watches for me" — the creation form came out entirely. The server
  action Muse uses stayed; the empty state now says to ask Muse.
  Graduated into rule 15 the same day.
- "The fare class should be a badge with an icon and the times of day
  could be slides with dots (like a bar and whisker)" — fare class
  became an icon badge, stops a dot-and-line badge, every leg got a
  24-hour time-of-day strip with departure and arrival dots and a
  +1 day marker on overnight legs, and each price got a range strip
  between its low and high ticks. Components over text, his examples
  treated as the pattern for the whole page.
- "More at a glance intuition — color language, icons,
  generative/visual representation and less walls of text where it
  makes sense to do so without feeling kitschy" — the governing
  principle for the component pass. Graduated into rule 14 the same
  day, kitsch guardrail included.
- "Some of the badge text is overflowing" — the badges carried
  nowrap and clipped against cards and a capped table cell. Fixed by
  wrapping inside the badge. A component is not done until it has
  been probed at real widths in both layouts.
- "Show dotted threshold lines for max/min" — the trend chart gained
  dotted reference lines at the watch's lowest and highest totals,
  labeled with their values in the min/max colors. Reference lines
  carry the range so the eye does not have to estimate it.
- "Can we use real airline logos? That will help for things like the
  legends" — genuine wordmarks (Wikimedia Commons SVGs, bundled) on
  small white plates that read in both schemes, leading the trend
  legend, the min/max footer, the table, the cards, and the settled
  panel. A carrier with no owned logo falls back to its name on the
  same plate, never a drawn imitation.
- "The legends have too much information, they just need the airlines
  and the tooltips can carry the detail" — minutes after the logos
  landed. The legend dropped to colour swatch plus logo plates; the
  fare brand moved into the tooltip. Legends identify; detail lives
  in tooltips. Folded into rule 14.
- "On Flight Watches the tooltips should also be using the airline
  logos" — the tooltip that received the detail also carries the
  identity: each tooltip entry is led by its colour swatch and the
  carrier's logo plates, with the fare brand beside them. Identity
  stays consistent at every level of the same chart.
- Asked which details.so vault items could elevate Flight Watches,
  he took the shortlist (number flow, pixelated transition,
  progressive blur, thinking orbs) and said "yeah try all of them."
  External detail libraries are a legitimate elevation source when
  each pick is matched against the page's own language first: the
  number flow went on the dominant price, the pixel dissolve speaks
  the halftone the backdrop already uses, the orbs replaced the
  refresh spinner. The ones that fought the approved design (liquid
  glass against the frosted panes, generic dot shapes duplicating
  the built dot language) were named and skipped. Trying is cheap;
  the judgment happens in the matching, and again on the result.
  The result, same day: the number flow stayed and drew "great,
  great little grace note"; the pixelated transition was cut on
  sight ("Remove the pixelated transition though") and removed
  whole — overlay, trigger, CSS, all of it, no vestige kept.
- "Can you animate the numbers whenever the page loads or
  transitions?" — minutes after the vault pass landed. A value
  animation that only fires on change is invisible most of the
  time; on his reading surfaces the numbers count up on load and on
  every view transition too, so the motion is part of arriving, not
  only of updating. Reduced motion still lands instantly.

## Earlier builds (from the standing record)

- Disk Space and Incident Ledger spaces: the Hallmark audit gate closed
  only when sloplint and plain-prose counts were run and reported, with
  waived flags named (frosted-glass blur and design color literals are
  waived as the design itself; mechanical flags get fixed).
- smolcast site push: the independent review caught three real defects
  (a clipboard race, a press timing over the site's own cap, a label
  scaling with its check) that the builder's own pass missed. Origin of
  the independent-review rule.
- Live-read verification: a page that reads a snapshot is not live, and
  saying so plainly is part of the report.

## Mined from the daily logs (Saturday, November 21, 2026)

Episodes pulled from the November 12–15, 2026 daily logs, after Evan
asked for lessons from previous design iterations to be learned properly.

- **A check that exits clean is not proof it ran** (November 13, 2026,
  skills review). Hallmark's render tier silently never runs on this
  machine but exits clean, so a build could be reported as passing a
  check that never executed. If a tier produced no output, the report
  says "not run." Same shape in the font builds (November 14, 2026):
  fontbakery was not installed, so it was reported as not run, never as
  passed, and the Cyrillic and Greek glyphs that ride along from the
  base fonts were reported as uncertified, never as checked.
- **Lint the authored source, not the build output** (Incident Ledger,
  November 13, 2026). The ledger's authored files reached 0 FAIL,
  0 REFLEX, 0 WARN while the whole tree still showed findings confined
  to platform scaffold CSS in the build output, which regenerates on
  every build. Scaffold findings get named as platform output in the
  report; build output is never hand-edited to satisfy a linter.
- **"Fix the cheap ones, waive the design ones"** (BishopPair command
  center, November 14, 2026; repeated November 15). Evan's triage, in
  his words. Cheap: the Hallmark stamp, a meta description, dashes in
  copy, padding off the 4px scale, a tracked uppercase tag, color
  literals that belong on tokens. Design: the glass blur and hairline
  warnings (gates 29 and F24) that flag the approved frosted glass
  itself, the design's own color literals, and middle-dot strings that
  are a channel's own post-copy style.
- **A restyle that lands unaudited is a debt that gets called in**
  (Disk Space, November 14–15, 2026). The night-foliage restyle shipped
  with the gate open twice; Evan had to order a separate no-change pass
  just to run the counters. The audit belongs inside the build brief.
  Companion failure from the same week: a builder's "audit passed" with
  no sloplint or prose counts in any record is not the gate, and counts
  hand-derived from source when a sandbox cannot run the tools are
  "probable, not confirmed" — never reported as run counts.
- **Contrast is reported per pair, against the worst surface** (Disk
  Space, November 14, 2026). Every text pairing carried its ratio:
  headline 10.0:1, muted labels 6.0:1, treemap labels 5.8:1 measured on
  the lightest tile, not the average tile.
- **Auto-playing motion needs a stop, and reduced motion is a JS rule
  too** (Disk Space, November 13, 2026). The scan animation auto-ran
  with no pause control (a WCAG 2.2.2 gap), and a misspelled
  reduced-motion query in the script meant the JS ignored reduced
  motion while the CSS honored it. Both halves get checked.
- **Small flags, exact fixes** (Incident Ledger, November 13, 2026).
  Pinch zoom restored by removing user-scalable=no; a 3px focus ring
  that clears 3:1 in both color schemes; overflow-x: clip on the shell;
  pressed states on buttons and fields; a real disabled style instead
  of an opacity utility.
- **Split the prose flags before reporting them** (Velvet command
  center, November 14, 2026). Of 10 plain-prose flags, 4 were real copy
  (em dashes, fixed) and 6 were the "—" empty-value placeholder in
  code, kept by design. And one Ledger flag was an extractor artifact —
  columns glued into a fake 49-word sentence — waived as an artifact
  after checking the rendered text. Check the rendered text before
  fixing copy that is not broken.
- **Tactics travel, vibes stay local** (November 14, 2026). Evan had
  the BishopPair and Velvet command centers elevated with the Disk
  Space restyle's tactics — frosted glass, token discipline, the audit
  gate — while each center kept its own distinct vibe and palette.
