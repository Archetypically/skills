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
