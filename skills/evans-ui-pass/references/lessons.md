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
