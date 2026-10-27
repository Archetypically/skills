---
name: game-design
description: Judges game designs against Riot's URF Academy game design curriculum (game feeling, 8 kinds of fun, goals and pacing, flow and core loops, resonance, depth vs complexity, playtest feedback) and wider modern design research (randomness and fairness, clarity, dominant strategies, economies and feedback loops, synergy, motivation, accessibility, dark patterns), with a cited research reference. Use when proposing or reviewing a mechanic, system, enemy, boss rule, economy change or screen; framing a design decision; diagnosing why something feels boring, unfair, pointless or confusing; or writing playtest feedback and post-mortems.
---

# Game design

A lens for **why** a design works, not **how much** (numbers belong to simulation and playtest data). Two sources:

- Riot's URF Academy course, which covers §1–§5 and the final-project material. The course text is not included here; §1–§5 are a distillate of it. First-party links are under Sources at the end of this file.
- `references/research.md`: modern design research from GDC talks, peer-reviewed papers, established books, designers' own writing and accessibility guidelines, every source tagged by how far it was verified. It covers §6–§10 and corrects §1–§5 where marked **(research)**.

Quote the source when a call rests on it: name the course module, or a `research.md` principle and its [S] source. Use your own judgement about whether to open the original course material: follow a link when a call rests on course detail, when the distillate here feels too thin for the decision at hand, or when the user asks what the course itself says. For a routine review, the distillate is enough.

The course's framework has five parts, and every design touches all of them:
**Player** (feeling, kinds of fun) → **Goal** (goals, subgoals, pacing) → **Decisions & Opposition**
(flow, core loop, satisfaction) → **Rules & Theme** (resonance, piggybacking, complexity) →
**Interaction** (depth, breadth, elegance).

## 1. Player: name the feeling first (URF Academy module 1)

- Design for **specific emotions**, then pick the kinds of fun that produce them. "Fun" alone is not a target. Interesting is not fun either: a mechanic can be clever to read and flat to play, so judge the feeling at the moment it pays off (research 7.7).
- The 8 kinds: **Sensation, Fellowship, Challenge, Fantasy, Narrative, Discovery, Expression, Submission.** Some blend (sensation + fantasy + narrative); **challenge and narrative clash**; submission rides on sensation.
- Name your game's profile before judging a design against it: which two or three kinds sit at the core, which carry them, and which target feelings they add up to. A Balatro-like, for example, runs **Challenge + Expression + Discovery** at the core, carried by **Sensation** and **Submission**, aimed at *clever*, *greedy triumph*, and *dread*.
- **Hard, but not unfair.** Frustration is acceptable when overcoming it feels earned. Where content is generated, prove it clearable; the live question is whether the *player* can see the way through.
- Audiences differ. The 8 kinds are a designer taxonomy; measured models back it up (§9). A difficulty ladder, where the player picks the rung, is one honest difficulty setting.

## 2. Goal: a goal at every timescale (URF Academy module 2)

Pace goals **moment-to-moment, game-to-game, session-to-session**, each with an appropriate reward.
Good subgoals let the player **measure progress towards a greater goal**; good goals create dynamic
states where **decisions change with the game state**.

An example ladder for a run-based game:

| Scale | Goal | Reward / ceremony |
| --- | --- | --- |
| Move | make the core move; complete a chain or combo | immediate feedback: score, replay, sound |
| Round | clear the round within its budget; beat par | cash out (prize, combo and strength bonuses) |
| Act | survive the next boss, visible ahead on the timeline | BOSS DOWN, the act prize |
| Run | clear the final act | run summary |
| Across runs | climb the difficulty ladder; fill the collection | next tier unlocked, entries revealed |

**Anti-patterns** to check every design against: analysis paralysis, **unclear optimization**, fun
not exceeding anti-fun, **false choices**, **expectation breaking**. A design that rewards an
optimum the player can't see (or punishes one they can) is the "come exactly 2nd" goal.

## 3. Decisions & Opposition: flow and the core loop (URF Academy module 3)

- **Flow is a sawtooth, not a ramp.** Each section starts low in the band, climbs to a **climax**, then gives **downtime** before the next rise. Small → big → boss is one sawtooth; the shop or rest stop is the downtime. Ask of any change: does it flatten the teeth or remove the trough?
- **(research)** Treat the sawtooth as a pacing default, not the whole difficulty strategy. Valve's Director varies pacing, not amplitude. Players want *progress feedback* to feel constant even while difficulty oscillates, so keep progress visible inside a valley (4.5, 4.9).
- **Boredom:** skill above difficulty for long, too much downtime, repetition without meaningful difference. **Anxiety:** difficulty above skill for long, too much complexity (boards, rules, **overloaded UI**), no downtime, time pressure, too many choices, exhaustion.
- In single-player, difficulty must rise **in tandem with mastery**. A generator or ramp has to track the player's growth, and its standing risk is that a build's growing power is never *felt*.
- **A boss must not be easy;** a consistent, always-hard climax builds the anticipation that makes it land.
- **Satisfaction = anticipation + decisive delivery + ceremony** (visual, auditory, tangible reward). Random big rewards are anticlimactic; earned ones aren't.
- **Balanced** means you can't tell who will win until the end. Runs ending on one bad round are a flow question, not only a numbers one.

**Five Whys** for every playtest or sim finding: chain "why?" from symptom to root cause before
changing anything. Write the chain down with the decision it feeds.

## 4. Rules & Theme: resonance and complexity (URF Academy module 4)

- **Complexity is a cost** (information needed to decide; sentences to explain), distinct from difficulty. Every new piece, rule or enemy spends it.
- **Piggyback** to buy complexity back: build on what the player already knows, and name mechanics so the name explains them (a pushing piece called Battering Ram teaches itself).
- **Resonance:** mechanics, names, art, sound and copy reinforce one idea. State your theme in one line and hold every choice to it (one game's version: *a draughts hustler working the parlour circuit*). A rule whose name or look fights what it does is a bug.
- Players bring expectations from the genre and from the games yours resembles. Breaking one needs a reason and a tell.

## 5. Interaction: depth over breadth (URF Academy module 5)

- **Depth:** decisions with meaningfully different outcomes. **Breadth:** options at once (2–5 is comfortable). **Elegance = depth ÷ complexity.** The worst design is high complexity with low depth.
- **(research)** Elegance means few concepts producing *interacting* loops, not few parts: one loop is rarely enough (5.2), and priorities should keep shifting (4.2).
- **Imbalance hides depth:** a dominant piece, a must-buy upgrade or an unwinnable boss draw is a depth problem as well as a balance one (§7).
- **Hide complexity until it is relevant:** the tutorial, fog of war on boss rules, and content gating do this.
- **Outcomes out of the player's control feel bad;** enemy phases and losses must trace to something the player could see and answer.
- **Comebacks:** if a run's end is clear halfway through, the back half is dead.
- Depth isn't always the goal: submission and sensation beats can be shallow on purpose.

## 6. Randomness and fairness (research §1B, 1.2, 1.6, 4.1)

- **Classify every random element.** *Input* randomness comes before the decision (board generation, shop offers, boss draws). *Output* randomness comes between a decision and its result (any chance-based effect). Output randomness cuts the link between a decision and its feedback, so keep it rare and visible (Burgun, Engelstein).
- **Input randomness fails too** when generated problems vary wildly in difficulty. Measure the *spread* of generated difficulty, not only its mean: proving and banding are the right tools (Burgun).
- **The folk rule "input good, output bad" is thin.** The one controlled study found input randomness least liked. Playtest generation directly, and let players see and plan around a generated problem before committing (Zhang et al.).
- **Players distrust randomness.** Show odds wherever chance decides. Prefer streak-limited randomness. Expect the generator to be blamed for losses (Meier, Pardo).
- **Players take credit for wins and blame the game for losses**, so every loss needs a visible cause: name it, and show a way through (Meier).
- **Give hedges.** Variance turns into a risk-management game. Rerolls, selling, previews and flexible pieces matter more than the average power level (LocalThunk).
- **What carries between runs is knowledge.** Generated content makes each run a skill challenge, not memorisation, so spend effort on legibility (Valve, Kasavin). Meta-progression evidence is thin: prefer unlocks that add options over unlocks that add raw power (research 1.9).

## 7. Decisions, dominance and synergy (research 4.2–4.4, 1.1, 1.4, 3.3)

- **The interesting-decision test.** Does the choice have more than one good answer that depends on the state? Make the optimal line the fun line (Meier, Rosewater #13).
- **Dominant-strategy audit.** Ask your bot or solver "does one build or heuristic always win?", not only "does it win?". A dominant strategy collapses the possibility space (Dormans).
- **Don't scale both sides evenly.** If targets and income rise together, the tension cancels out (Into the Breach).
- **Generated content guarantees options.** "No options whatsoever" is the most frustrating state. A generator should guarantee at least one proven line through; aim for more than one meaningful line where cheap (Ma).
- **Strong combos are a goal in single-player.** Guard them with counter-pressure that hits *different* archetypes (boss rules, counters), not with caps (Giovannetti).
- **Two failure tests per piece:** it *cannibalises neighbouring strategies*, or it is *never worth taking*. Tune with one numeric knob in data (LocalThunk).
- **Tag each piece by psychographic** and keep a spread: Timmy (big effects), Johnny (expression through odd builds), Spike (proving skill; the hard modes) (Rosewater).

## 8. Economy and systems (research §5)

- **Positive loops snowball; negative loops stabilise.** Decide where your friction bites, so runs neither snowball nor get decided in the first rounds (LeBlanc via Dormans).
- **Pair every engine with friction.** The player should always balance at least three things (Dormans; Machinations).
- **Value chains end in an anchor.** Money matters only through what it buys, ending in something intrinsically rewarding. "X feels pointless" is a broken chain. Match source growth to sink growth, or late money goes dead (Cook). Add sinks in the same change that adds faucets.
- **Emergence vs progression:** synergies are emergence, levels and boss rules are progression. Keep the progression authored and the emergence free (Juul, Dormans).
- **Two kinds of balance:** transitive (cost curves: power against price) and intransitive (counters: boss rules against archetypes). Bot-based evaluation is a recognised method (Schreiber and Romero; Jaffe et al.).
- **Metrics inform, they do not decide.** Pick rate and win rate are confounded by when an option is offered, so compare like for like. Paired-seed sims handle this well (Giovannetti).

## 9. Clarity, feel and motivation (research §2, §3)

- **Clarity is a deletion rule.** If an effect can't be shown by a short animated preview, redesign or cut it (Into the Breach). Hold a text budget: Balatro's jokers fit in four lines and 20 words (LocalThunk).
- **Telegraph consequences, and test the telegraph on fresh eyes.** The designer can't judge clarity; a naive playtester can.
- **Keep one unmistakable gauge** (score against target, moves left, money) so everything else may shift.
- **Juice is maximum output for minimum input, and it should carry information** (which piece fired, how much), as a layer with fast-forward and reduced-motion controls (Jonasson and Purho; Swink; XAG 117).
- **Meaningful play is discernable and integrated:** could the player tell what happened, and does it change what they do next? (Salen and Zimmerman.)
- **Self-Determination Theory:** competence, autonomy and relatedness each predict enjoyment. Shop choice is autonomy, clear scoring is competence, and in a single-player game seeds and shared runs may be the only relatedness hook. Use rewards as information, not control (Ryan, Rigby, Przybylski).
- **Measured motivations** (Quantic Foundry): name the ones your game serves (for example Strategy, Challenge, Power, Completion, Design, Discovery) and cut first the ones it doesn't.
- **Ownership and discovery bind players:** a player's build is their identity, and they value what they found themselves. Leave some synergies undescribed (Rosewater #9, #10).
- **Losses loom larger than gains.** Frame a harder mode as an added rule, not a removed reward. Be careful with money penalties, forced sales and price jumps (Kahneman and Tversky; Hopson).
- **Onboarding:** treat text volume as cognitive load, teach one mechanic at a time, and reward the first minutes generously (Sweller; Meier).

## 10. Accessibility and ethics (research §6, §8)

- **Never colour alone:** pieces, enemies and markers need a shape or icon channel, and every cue needs a second channel, visual and audio (GAG; XAG 103).
- **Undo or confirm before destructive actions** (selling, ending a round, the last coin) (XAG 115).
- **Untimed decisions; game speed and reduced motion** are baseline options (GAG; XAG 116, 117).
- **Player-set, non-judgemental difficulty** that can change between runs; name modes without judgement (Celeste; XAG 108). APX's challenge patterns (House Rules, Undo Redo, Slow It Down, Training Ground, Total Recall) are a ready vocabulary.
- **Include impaired players in playtests** (GAG).
- **No dark patterns** in a premium game: no grinding that gates content, no decaying streaks or appointment mechanics that punish absence, nothing random bought with real money, and no slot-machine presentation (Zagal, Björk and Lewis; Hopson; LocalThunk).
- **Respect the player's time:** fast restarts, skippable animation, bounded runs (Meier).

## Evaluating a design

Score a proposal 1–5 on each axis with a sentence of reasoning, and record the table with the proposal:

| Axis | Question |
| --- | --- |
| Innovation | Is it new to this game? Would it delight? |
| Depth | Does it create decisions that change with the game state? |
| Dominance | Could it become the one build or move that always wins, or the one never taken? |
| Complexity | How many sentences, and does it fit the text budget? Can it be shown animated? |
| Cohesion | Do name, look, rule, kind of fun and feeling agree? |
| Fairness | Is its randomness input or output? Can the player see odds and causes? |
| Economy | Which loop does it feed or drain? Does it keep sources and sinks matched? |
| Satisfaction | Is acting on it satisfying (emotion, not just interest)? Which feeling does it serve? |
| Access | Does it rely on colour, timing or sound alone? |
| Cost | Can we build, tune (sim) and explain it at its value? |

Start every iteration with an **explicit goal** ("make the shop decision harder", not "improve the
shop"), then judge the result against that goal.

## Playtests, feedback and post-mortems (URF Academy final project; research §7)

- Write **test goals** before a playtest and give testers the minimum briefing.
- **Players diagnose; designers prescribe.** Keep a player's symptom; discount their proposed fix, then find the structural cause (Rosewater #19).
- Report findings as **"I experienced X, which did not match Y because Z"**, tied to a goal or feeling. Name the problem; offer a fix only as an *example*.
- **What a player feels is not wrong.** Record the feeling even when the design intends otherwise.
- **Fresh eyes per milestone,** not per release: the team cannot see its own telegraph problems.
- **Cull hard and use constraints on purpose** (words per piece, effects per piece). A violation is a bug (Giovannetti; Rosewater #18).
- Prioritise fixes by criticality. Check rules **as a cheater would**: solver lines and a run bot are the strongest cheaters, if you have them.
- **Simulation displaces paper for balance;** paper or quick mock-ups still win for first-impression clarity.
- Post-mortem prompts: went well, went poorly, harder than expected, easier than expected, key decisions and why, process changes. No personnel blame.

## Sources

§1–§5 and the playtest material distil Riot Games' **URF Academy** game design course (© Riot Games, published under CC BY-NC-SA 4.0; adapted from a college course by Stone Librande). The course text is not included in this repo. Read the original at Riot's own pages:

- Course home: https://www.riotgames.com/en/urf-academy
- The curriculum, every module with its PDF: https://www.riotgames.com/en/urf-academy/the-curriculum
- Curriculum guide and glossary: https://www.riotgames.com/en/urf-academy/curriculum-guide
- Module 1, Game Feeling & 8 Kinds of Fun: https://www.riotgames.com/en/urf-academy/fun-and-feeling
- Module 2, Goals & Pacing: https://www.riotgames.com/en/urf-academy/goals-and-pacing

§6–§10 distil `references/research.md`, which lists its sources with verification tags.
