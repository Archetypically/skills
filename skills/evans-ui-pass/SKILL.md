---
name: evans-ui-pass
description: Evan's UI pass — the design iteration method distilled from his corrections across web builds. Use on any UI build, edit, or design review for Evan: run the installed skills for real, apply his taste rules (real photography over drawn scenes, system light/dark, transparent frosted panes, no slop tells, strict hierarchy, disciplined color language), verify with measured contrast and the Hallmark audit gate, report per skill, and distill new nudges back into this skill in the same pass.
---

# Evan's UI pass

A pass is not done when it looks better. It is done when every skill below
actually ran, the audit gate closed, and the report names what each skill
changed and what was not verified.

## Run the real skills, never their vibes

- A named skill counts as run only when its installed files were read and
  applied to the work. Briefing a builder with a skill's principles from
  memory is not running it, and the report never claims it was.
- If a skill Evan names is not installed, say so plainly, then install it
  properly before the pass continues. His catalog vendors upstream skills
  (Hallmark; Emil Kowalski's animation and design set; Jakub Krehel's
  better-* family) — vendored copies are byte-identical to upstream and
  registered in the vendored-skills manifest.
- The standing set for a web build: Hallmark (sloplint audit), Emil's
  design-eng and animation skills, and the better-* family — better-ui,
  better-colors, better-typography, better-layout, better-motion,
  better-accessibility, better-writing, with better-interface last as the
  umbrella sweep.

## The audit gate

- The gate runs inside the build brief, not as a follow-up pass. A
  restyle that lands unaudited is a debt that gets called in.
- Run Hallmark sloplint on the source and plain-prose on the UI copy.
  Report both counts. 0 FAIL is the bar.
- Evan's triage, in his words: fix the cheap ones, waive the design
  ones. Mechanical flags (stamp, meta, dashes in copy, off-scale
  padding, untokenized colors) get fixed. Flags that are the approved
  design itself get waived, each by name with its reason. A waiver is
  never silent.
- A tool that exits clean is not proof it ran. A check tier that
  produced no output — the render tier silently never runs on some
  machines — is reported as not run, never as passed.
- Scope lint to the authored source. Findings in platform scaffold or
  build output are named as such in the report; build output is never
  hand-edited to satisfy a linter.
- A count taken inside a builder's verification pass is reported as
  exactly that, not as an independent run. Counts derived by hand when
  the tools cannot run are "probable, not confirmed," never run counts.
- An agent that did not make the change reviews it before it is reported
  as done. A failed review is a failed build.

## Measure, do not estimate

- Contrast is computed on the rendered pairs, in both color schemes,
  including text over translucent surfaces and over photographs. The bar
  is 4.5:1 for body text. A value that "looks fine" is not a measurement
  (better-colors once caught 2.66:1 text that looked fine).
- If a scheme or state could not be rendered, say how it was verified
  instead (source values, computation) and name it as not seen.
- Live-read rule: a page reads its source live only when the built path
  asks the source on open, with no snapshot in between. Prove it by
  changing a value and watching the page change. Verify the shipped
  artifact itself, not the intent files behind it.

## Evan's taste rules

1. **Real photography beats drawn scenes.** CSS-gradient skies and clouds
   read as slop. Scenic backgrounds come from real stock (Pexels is the
   standing source). Judge the frames themselves, never the listing
   description.
2. **Follow the system.** `prefers-color-scheme`, no manual toggle. Light
   and dark are both full designs in the same language, not one design
   and its inversion.
3. **Frosted glass stays honest.** Panes are very transparent but not
   totally transparent: the scene shows through, and a hairline border
   holds the pane's shape. Strong backdrop blur does the legibility work.
4. **No slop tells.** No halftone or dot-grain overlays laid over a
   finished design. A photograph rendered as a dithered halftone of
   itself is a named treatment, not an overlay — Evan asked for it by
   name from his Tidbits (the morrre_dsgn reference) on Flight Watches.
   No random per-item colored glows. No rows of pill-shaped chips or controls —
   pills scream slop. Controls are quiet: small radius, hairline border,
   plain text, subtle hover.
5. **Chrome earns its place.** Summary totals live as small badges next
   to the page header. "Last updated" and other metadata live in a
   footer. A summary pill row at the top of a page is banned.
6. **Hierarchy at a glance.** A strict scale: page title, then the
   thing's own name (on Flight Watches, the route codes), then one
   dominant number (the current price). Secondary data — minimums,
   maximums, per-person figures, dates — is visibly quieter in size and
   tone. Route, current price, and lowest-status read within two seconds
   per card. Group by spacing first, lines second, boxes last.
7. **Color is a language, not decoration.** Neutrals do the structural
   work. One accent, reserved for interactive elements and the pick
   marker. Semantic colors keep one fixed meaning on every page and in
   every chart: price down is good (teal/green family), price up is a
   warning (warm amber/red family), unchanged is neutral. Same hues in
   both schemes, adjusted only for contrast. Chart colors come from the
   same vocabulary. Chart axes do not exaggerate: the Y axis starts at
   0, so a small price move reads small.
8. **Type with character, numbers with discipline.** A display serif for
   headlines and big numbers (Hedvig Letters Serif is the current
   favorite), a clean sans for body and tables. Tabular numbers on every
   price and chart axis. Form text is 16px on small screens so iOS does
   not auto-zoom.
9. **Motion follows Emil's rules.** Fast ease-out, under 300ms,
   transform and opacity only, stagger 30–50ms. Reduced motion
   cross-fades instead of killing motion. A color-scheme change never
   animates, so colors do not smear. When a skill's exact value conflicts
   with a consistent project convention, the convention can win — the
   report says so and says why.
10. **Copy is plain and unambiguous.** Short sentences, sentence case,
    verb-first buttons. A UI word that means something else in the
    domain is banned: the explainer once used "Delta" for a price
    difference on a page where Delta was also an airline. UI words never
    collide with domain nouns.
11. **Accessibility is a floor, not a pass.** Main landmark, focus moves
    into a detail view and returns cleanly, load errors announce with
    role=alert, hit areas and accessible names pass, focus ring visible.
    Pinch zoom is never disabled. Anything that auto-plays gets a stop
    control, and reduced motion is honored in the JavaScript as well as
    the CSS.
12. **Named treatments are applied for real.** When Evan names a font, a
    texture, a photo, or a library from his Tidbits, the build uses that
    actual thing. An approximation is a different design decision and is
    reported as one.
13. **Tactics travel, vibes stay local.** A treatment that works on one
    of Evan's surfaces (frosted glass, token discipline, the audit gate)
    ports to the others. Each surface keeps its own palette and mood;
    nothing gets reskinned into a house clone.
14. **At-a-glance intuition beats text walls.** Where a visual carries a
    fact faster than a sentence, the visual ships: semantic color, icons
    with one fixed meaning, and small generative visuals (time-of-day
    strips, price range strips, dotted min/max threshold lines). Text
    walls get cut where a component carries the same fact; exact numbers
    stay as text. Legends identify; detail lives in tooltips. The
    guardrail is Evan's: never kitschy. No decorative icon clutter, no
    novelty shapes — every visual earns its place by making something
    readable at a glance, or it does not ship.
15. **His surfaces are for reading; creation is agent work.** Evan asks
    Muse to put data in. He does not use self-serve forms, so his
    personal spaces carry no new-item flows or entry forms. The write
    actions stay on the server for Muse to use, and an empty state
    says to ask Muse.

## Reporting

- One report per pass, brief first: what changed, per skill — what it
  changed, or that it found nothing. Waivers named. Unverified items
  named. Then the completion card.
- The report is written in Evan's plain style: short sentences, actor as
  subject, no stock phrases.

## The learning loop

This skill improves by being corrected. After every design iteration
task:

1. Distill each new nudge, correction, or taste call from Evan into
   `references/lessons.md`, dated, with the task named.
2. A lesson becomes a rule in this file when Evan repeats it, or when it
   decided an outcome. One-off preferences stay in lessons.md.
3. When a new nudge conflicts with a rule, the nudge wins and the rule is
   rewritten. Rules are never layered over each other.
4. Update every copy in the same pass: this repo (Archetypically/skills)
   is the source of truth, the local skill catalog mirrors it, and the
   update is pushed and verified before the task is reported done.
