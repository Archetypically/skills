# Modern design research: what the URF Academy lens misses

Compiled 2026-10-27 from high-quality sources only (GDC talks and their official write-ups, peer-reviewed work,
established books, designers' own writing, accessibility guidelines). Our own synthesis with citations; quote the
source, not this file, when a call rests on it. `../SKILL.md` §6–§10 distil it.

Scope: extend the game-design skill beyond the Riot URF Academy curriculum (8 Kinds of Fun / MDA, goals and pacing, flow and the sawtooth, core loops and ceremony, Five Whys, resonance and piggybacking, complexity as a cost, depth/breadth/elegance, paper prototyping, playtest feedback, post-mortems).

Worked example used for the "why it matters" lines: a Balatro-like checkers roguelike - a stack of scoring pieces (points x multiplier), generated boards, a move budget, a cash-out and shop step between rounds, boss-rule championships (about 16 rounds), a difficulty ladder, premium single-player.

## How to read the source tags

Every source has an ID like [S12] and a status. The full list is at the end.

- **P**: I fetched the text and read it (paper, article, talk write-up, official page).
- **L**: existence and metadata verified (talk title, venue, year, or book record), but I did not read or watch the content. Content claims for these come from a P source that describes them.
- **S**: content known only secondhand (another source's description of it). Claims are phrased accordingly.
- **B**: bibliographic record only (Crossref or publisher), checked that it exists. Any claim made from it is background knowledge of a famous result, and is marked.

Access limits to know about:
- GDC Vault pages are a JavaScript app that was in "maintenance" when I fetched, so no GDC Vault talk content was readable. Talks are verified through GDC/Game Developer write-ups and YouTube titles (checked via oEmbed), and marked L.
- I could not watch videos or read transcripts. Talk content is therefore cited from the write-ups I did read.
- jesperjuul.net, Hunicke's Northwestern pages and Quantic Foundry's blog were unreachable or blocked. Juul is cited via his DiGRA record plus Dormans citing him. Quantic Foundry is cited via its fetched reference PDF.
- Meta-progression (area 1) has weak developer-authored evidence. I say so there rather than pad it.

**Attribution correction.** The brief mentions "Garfield, Totilo/Engelstein" for input vs output randomness. The terms are credited to Geoff Engelstein (Ludology/GameTek ep. 183, 2018) by Zhang et al. [S1], and Keith Burgun [S2] uses the same terms in 2014. I found no source tying Garfield or Totilo to the input/output framing. *Characteristics of Games* (Elias, Garfield, Gutschera, MIT Press; hardcover ISBN 9780262017138, seen in a retail listing only) has chapters on randomness and luck/skill, but I could not read it. Do not cite Garfield for the input/output split.

---

## 1. Roguelike and deckbuilder design (run structure, synergy, variance, randomness)

**1.1 In a single-player deckbuilder, let combos be strong, but build counter-pressure so there is no single dominant build.**
Giovannetti: combos are "a hallmark of our design process", and single-player means "we don't have to worry about the typical downside of strong combos - where the opponent feels bad". The same interview says the enemy roster was built so "there would not just be a single dominant strategy", and the player must "keep multiple things in mind" when building.
*Why it matters:* "Broken" stacks are fine as a goal, so judge boss rules and coups by whether they pressure different archetypes, not by whether they cap power.
Sources: [S3].

**1.2 Randomness in a roguelike turns into a risk-management metagame, so give players hedging tools.**
LocalThunk observed that discourse on "how random the game feels" shifted toward "mitigating risk and having a build that can't be easily countered while still being powerful enough to win", and admitted "there is a lot of randomness, possibly too much".
*Why it matters:* Board generation and shop offers are the variance. Rerolls, selling, previews and flexible chips are the hedges, and they matter more than the average power level.
Sources: [S4].

**1.3 Cap content complexity with a hard text budget, and let the budget shape the content.**
Balatro's rule: joker descriptions "can't be more than four lines and 20 words". LocalThunk says simplicity "kind of breeds this elegant strategy by itself". He also says the poker theme was added "mainly as an onboarding tool" (iconography the player already knows).
*Why it matters:* A chip, coup or boss rule that needs a paragraph is a design failure. Checker iconography is the equivalent onboarding crutch.
Sources: [S5], [S4].

**1.4 Tune with single numeric knobs, and use "cannibalises neighbours" and "never taken" as the two failure tests.**
LocalThunk: a card is a problem if it "cannibalises all the adjacent strategies" or is "so bad that there are few reasons to ever take it". He says "almost all balance changes can be made by changing a number" and that he balances "by feel" (his picture-frame analogy: it should feel level, not be technically level).
*Why it matters:* Keep chip values as data fields (Resources). The test per chip is "does it crowd out its neighbours" rather than "is the number fair".
Sources: [S4].

**1.5 Add a cheap strategic layer above the combat layer (path or schedule choice) for risk/reward without much complexity.**
Giovannetti on the Spire map (inspired by FTL): "layered decision-making ... adds an extra element of risk/reward and planning ... without a ton of complexity."
*Why it matters:* Which heat or shop to commit to, and boss previews, give planning depth at near-zero rules cost.
Sources: [S3].

**1.6 Procedural variation should make each run a skill challenge, not a memorisation exercise; the thing that carries over between runs is player knowledge.**
Valve: static placement "hinders replayability" because players memorise it; procedural population makes a session "a skill challenge instead of a memorization exercise". Kasavin: even in the hardest roguelikes "there is in fact, something that you carry forward, which is your knowledge of the mechanics". The Berlin Interpretation says the random environment "makes [permadeath] enjoyable rather than punishing".
*Why it matters:* Generated boards are the point of the genre. Spend the effort on legibility so knowledge accrues, not on curated difficulty.
Sources: [S6], [S7], [S8].

**1.7 Seeds are a social feature, and players will use them in ways the designer did not expect.**
LocalThunk exposed the seed almost as an afterthought; players "really, really got into the seeds", and he changed the seed algorithm to suit what they enjoyed after talking to them.
*Why it matters:* Cheap relatedness for a single-player game (shareable run codes, daily seed, challenge seeds).
Sources: [S5].

**1.8 The Berlin Interpretation is a useful checklist, not a mandate.**
High-value factors it lists that the example game already has: random environment generation, turn-based, grid-based, complexity ("enough item/item interactions" for several solutions), resource management. It says shops that switch mode are a "non-modal" violation. It states its purpose is understanding, "not to place constraints on developers".
*Why it matters:* Confirms the genre lineage. The modal shop and meta-layer are a known deviation, not a defect.
Sources: [S7].

**1.9 Honest gap: meta-progression.**
I found no developer-authored primary source (GDC, Game Developer, or interview) that rationalises permanent upgrades. Only Kasavin on difficulty walls and carried knowledge ([S8], [S9]) is solid. Treat any skill guidance here as inference: prefer unlocks that add options over unlocks that add raw power.

### 1B. Randomness: input vs output, variance, and fair-feeling luck

**1.10 Definitions.**
*Input randomness* gives the player random information before they decide (map generation, card draw). *Output randomness* is noise injected between the decision and the result (dice combat). They sit on a continuum. Burgun argues output randomness "does not belong in a strategy game" because it cuts the link between decision and feedback.
*Why it matters:* Know which of your random elements is which. Board generation is input randomness. Any chance-based chip effect is output randomness.
Sources: [S2], [S1], [S10] (L, Engelstein GDC 2018).

**1.11 Input randomness fails too, when the player has little time to respond or when generated problems vary wildly in difficulty.**
Burgun: "irresponsible use of input randomness - where the player has very little time to respond to the new information, or where the game generates problems of wildly varying difficulty match to match - cause similar problems as output randomness."
*Why it matters:* This is the written case for generator difficulty banding and deal-proving. The metric is spread of deal difficulty, not mean deal difficulty.
Sources: [S2].

**1.12 The folk rule "input good, output bad" has thin empirical support: the one controlled study found the opposite for input randomness.**
Zhang et al. (n=18, one custom collectible card game, four conditions) found the input-randomness-only version was the least liked (conditions without input randomness scored higher, though the drop did not appear in the combined input+output condition), with no significant effect for output randomness or the interaction. Participants valued being able to plan, but one said that without randomness he could "make a perfect plan" and the game was too easy. The authors flag the study as underpowered and limited to a single game.
*Why it matters:* Do not treat the heuristic as law. Playtest board generation directly, and keep a way for players to see and plan around the board before committing.
Sources: [S1].

**1.13 Players distrust randomness; show odds and expect to be second-guessed.**
Meier (GDC 2010, as reported): "Whenever something random happens to the player, paranoia sets in"; players feel "the computer rolled that random number just to be difficult". For Civilization Revolution he displayed combat odds and found testers expected to win every 3:1 fight despite a 25% loss chance; he altered the maths, including factoring in recent outcomes. Pardo (WoW) shipped increasing drop chances after each failed kill because players blamed the generator for cold streaks. (The Civ Rev and WoW details are from a news write-up, S.)
*Why it matters:* If any outcome has chance in it, show the odds, and prefer streak-limited randomness. Whether to bend the numbers is a trust call, not a pure maths one.
Sources: [S11] (P), [S12] (S).

**1.14 Where to look for the toolbox.**
Schreiber and Romero's *Game Balance* has chapters titled "Pseudorandom Numbers", "Human Intuition", "Managing Luck and Skill". Engelstein's GDC 2018 talk catalogues "white, brown, and pink" randomness plus input and output randomness. I read the tables of contents and listings only.
Sources: [S13] (L), [S10] (L).

---

## 2. Juice, game feel, readability and clarity

**2.1 Feel is a designable layer, not a coat of paint.**
Swink's book frames "feel" as a hidden language of design with six key components, covering sound, ancillary indicators, metaphor and perception. His definition is real-time control, so for a turn-based game this applies by analogy: input-to-response latency, and polish on piece moves, captures and score tally.
*Why it matters:* The scoring cascade is the game's "feel" moment, not the move itself.
Sources: [S14] (L).

**2.2 Juice is "maximum output for minimum input"; stack cheap feedback on top of readable state changes.**
Jonasson and Purho (GDC Europe 2013): juicy things "wobble, squirt, bounce around, and make little cute noises"; "if a game's juicy ... it feels more professional. It doesn't matter if the graphics are crappy." Nijman's *Art of Screenshake* (INDIGO Classes 2013) stacks many small feedback tweaks on a dull prototype (secondhand: I read no write-up of its contents).
*Why it matters:* Per-chip trigger feedback during scoring should feed information (which chip fired, how much) as well as spectacle.
Sources: [S15] (P write-up), [S16] (L).

**2.3 Provide controls for the juice itself.**
XAG 117 requires being able to pause or stop moving or auto-updating content and customise camera and screen-movement settings. GAG Basic says "avoid flickering images and repetitive patterns"; Advanced says avoid "any sudden unexpected movement or events". GAG Basic also says to include an option to adjust game speed.
*Why it matters:* A fast-forward and reduced-motion option for scoring cascades is a baseline, not a nice-to-have.
Sources: [S17], [S18].

**2.4 Clarity is a hard design constraint that removes content.**
Into the Breach's Justin Ma: "As a game design principle, we would sacrifice cool ideas for the sake of clarity every time." They cut weapons and firing patterns that could not be conveyed to playtesters. Their most important decision, he says, was animated tooltips: "showing that little animation of them moving is a thousand times more effective" than text.
*Why it matters:* Every chip, coup and boss rule should be previewable by a short animation of its effect on a sample board.
Sources: [S19], [S20].

**2.5 Telegraph consequences, and test the telegraph on fresh eyes.**
The game shows what every enemy will do before it does it. Ma: the team was "fine with" cluttered damage indicators "because we knew exactly what every enemy did", but "as soon as we handed it to someone else, we needed to make it very clear who was doing what."
*Why it matters:* Score previews (chips x mult before commitment) and boss-rule previews are the equivalent. The designer cannot judge clarity; naive playtesters can.
Sources: [S19], [S20].

**2.6 Keep one unmistakable top-level gauge so everything else may shift.**
In Into the Breach, the Power Grid is always clear, and "its clarity allows the rest of your priorities to constantly shift so you're rarely sure of your best move while also knowing what's genuinely bad."
*Why it matters:* Target score, moves left and money must stay legible so chip interactions can be arbitrarily clever.
Sources: [S20].

**2.7 Make the details and "pointless" extras generous; you can't predict which ones will land.**
Kasavin: "the unnecessary, pointless things ... can make a game very special ... we as a developer don't actually know which ... a player is going to really respond to." Rosewater lesson 8: details are where players fall in love with a game.
*Why it matters:* Cheap flavour text, chip names and idle animation are worth the budget and cost nothing in rules complexity.
Sources: [S8], [S21].

**2.8 Meaningful play needs results to be both discernable and integrated.**
Salen and Zimmerman's definition (*Rules of Play*, 2004, from my knowledge of the book; I did not fetch it, though [S22] cites other passages of it). Discernable: the result of an action is communicated. Integrated: it affects later play.
*Why it matters:* A useful two-question check for each feedback element: could the player tell what happened, and does it change what they do next?
Sources: [S23] (L).

---

## 3. Player psychology: motivation, loss, reward schedules, cognition, onboarding

**3.1 Self-Determination Theory is empirically grounded in games: competence, autonomy and relatedness each predict enjoyment and future play.**
Ryan, Rigby and Przybylski (four studies) found perceived in-game autonomy and competence associated with enjoyment, preference and well-being change. In the multiplayer sample, autonomy, competence and relatedness "independently predict enjoyment and future game play". They add that autonomy support looks like choice, rewards used as "informational feedback (rather than to control behavior)", and non-controlling instructions, and that intuitive controls relate to competence and autonomy.
*Why it matters:* Audit each feature against the three needs. Shop choice is autonomy; clear score feedback is competence; seeds and shared runs are the only relatedness hook.
Sources: [S24], [S25].

**3.2 Motivation is plural; use an empirical map instead of a typology of fun.**
Quantic Foundry's model is derived by factor analysis (about 1.25M gamers in the fetched 2019 reference) and has 12 motivations in six pairs: Destruction/Excitement, Competition/Community, Challenge/Strategy, Completion/Power, Fantasy/Story, Design/Discovery. The Mastery-Achievement cluster ("Let Me Think", "I Want More") is described as cool-headed, long-term, cumulative.
*Why it matters:* The example game serves Strategy, Challenge, Power, Completion, Design (build expression) and Discovery. Action, Social and Story are the cut features if you must cut.
Sources: [S26], [S27] (B).

**3.3 Design components for specific psychographics: Timmy (big effects), Johnny (self-expression through unusual builds), Spike (proving skill).**
Rosewater's research-derived profiles, with most players being hybrids. Johnny "enjoys deckbuilding as much as (or more than)" playing and wants to win "on his own terms"; Spike "values competition" and cares about wins. Lesson 15: design each component for its intended audience.
*Why it matters:* Tag every chip with the profile it serves and keep a spread. Stakes are for Spike; weird combo chips are for Johnny; big-number chips are for Timmy.
Sources: [S21], [S28].

**3.4 Ownership: players attach to what they built.**
Rosewater lesson 9: their deck is "an extension of themselves", and "customization isn't just a way to crowd-source content, it's a means to give players the tools to make your game personal." Lesson 10: leave room to discover things, because players "are more invested in things that they initiated".
*Why it matters:* The stack is the identity. Show it (names, history, run summary), and let some synergies be discoverable rather than described.
Sources: [S28].

**3.5 Losses loom larger than gains, and a reduction from an established level is punishing; framing counts.**
Kahneman and Tversky (1979) is the foundation. Games-specific: Hopson (Bungie user research): "reducing the level of reinforcement is a very punishing thing for your players"; "sudden loss of reward is very aversive". Pardo's Rest XP (as reported, S) was the same maths reframed from a penalty to a bonus.
*Why it matters:* Frame a harder stake as a new rule or added pressure, not as removing something the player already had. Be careful with money penalties, forced sales and shop-price jumps.
Sources: [S29] (B), [S30] (P), [S12] (S).

**3.6 Ownership inflates value (endowment effect) and the end of an experience weighs heavily (peak-end), by analogy.**
Kahneman, Knetsch and Thaler (1990), and Kahneman et al. (1993; a pain study, so applying it to games is an analogy). My inference: the sell price of a chip will feel like a loss relative to the buy price, and the cash-out and run-end screens carry disproportionate weight in memory.
*Why it matters:* Spend polish on cash-out and run-end; test sell-value perception explicitly.
Sources: [S31] (B), [S32] (B). Inference marked.

**3.7 Know your reward schedule, and use it knowingly.**
Hopson: variable-ratio schedules produce "the highest overall rates of activity"; fixed-ratio schedules produce a pause after each reward (a point where players quit); sudden reward removal ("extinction") produces frustration; "avoidance" schedules (things decay unless you act) create momentum cheaply.
*Why it matters:* Shop rerolls and chip offers are variable-ratio. That is fine in a premium game, but make the choice deliberately and keep it out of anything that costs real money (see area 8).
Sources: [S30].

**3.8 Treat cognitive load and onboarding as design constraints.**
Cognitive load theory (Sweller, 1988) and Hodent's *The Gamer's Brain* are the standard references (Hodent: retail listings only, S). Practical expressions found in primary sources: Balatro's 20-word cap [S5]; Into the Breach's animated tooltips [S19]; GAG Basic: "include interactive tutorials", "use simple clear language", "allow the game to be started without the need to navigate through multiple levels of menus". Meier (2010, as reported): "You almost cannot reward the player enough" in the first 15 minutes.
*Why it matters:* Teach one mechanic at a time inside early heats and reward the first minutes generously. Treat text volume as load.
Sources: [S33] (B), [S34] (L/S), [S5], [S19], [S18], [S11].

---

## 4. Difficulty and fairness

**4.1 Players take credit for wins and blame the game for losses, so losses must have visible causes.**
Meier (GDC 2010, as reported): players "are very much inclined to accept anything you give them and gladly feel it was their own incredible play"; if they lose, "the blame often falls on the game". His "winner paradox": players expect to win in some form.
*Why it matters:* The run-ending screen should name the cause (what the target was, what the stack did), not just "you lost".
Sources: [S11].

**4.2 The interesting-decision test and the dominant-strategy audit.**
Meier's GDC 2012 talk revisits his line that a game is a series of interesting decisions. Dormans: dominant strategies "effectively narrow the broad possibility space ... into a single confined path". Rosewater lesson 13: "make the fun part also the correct strategy to win". Ma (Into the Breach): "If it's just a simple experience where in every situation you want to do the same choice, it's not much of a game."
*Why it matters:* Extend the run-bot sims from "does it win" to "does one build or heuristic always win", and make sure the optimal line is also the fun line.
Sources: [S35] (L), [S22], [S28], [S36].

**4.3 Do not scale both sides evenly: the decision disappears.**
Subset found that a scaling-up health bar stopped mattering ("it's always worth the collateral damage"), and scaling buildings, damage and recovery together was pointless: "Why are we even scaling it if absolutely everything has to scale evenly? Just keep it all low!"
*Why it matters:* Be wary of a stakes ladder that multiplies target and income together; the tension you wanted cancels out.
Sources: [S36].

**4.4 The most frustrating state is "no options whatsoever", so generated content needs a guarantee.**
Ma: "The most frustrating thing that can happen is to have situation where you have no options whatsoever to resolve." Subset hand-designed 8x8 maps for control and learned layout rules (e.g. avoid certain building arrangements).
*Why it matters:* Generator invariants ("always at least N viable lines") are the right kind of guardrail and deal-proving is the right idea. Add "player has more than one meaningful option" as a testable invariant.
Sources: [S36].

**4.5 Dynamic difficulty: prefer adjusting pacing over amplitude, and keep it trustworthy.**
Hunicke and Chapman's Hamlet (2004) adjusts a first-person shooter's difficulty at run time from player performance (abstract: games are boring when too easy and frustrating when too hard). Valve's Director estimates "emotional intensity" and says its "algorithm adjusts pacing, not difficulty. Amplitude (difficulty) is not changed, frequency (pacing) is."
*Why it matters:* A stakes ladder is the opposite of hidden DDA; if any adaptivity is added, vary heat pacing and offers rather than secretly shifting target scores.
Sources: [S37] (L/S), [S6].

**4.6 Let the player set difficulty openly, and word it without judgement.**
Celeste's Assist Mode was "Cheat Mode" until the designer found that "judgmental"; its stated aim is to "help players find the challenge level that's right for them" so they "come out of this game feeling capable and powerful". XAG 108: provide difficulty presets (ideally four or more), allow changing "at any time without losing game progress", and allow adjusting difficulty of different mechanics separately.
*Why it matters:* Treat stakes plus custom house rules as an autonomy feature. Name modes carefully and allow changing between runs (and consider mid-run).
Sources: [S38], [S17].

**4.7 Fail forward: lower the cost of losing, and carry something forward.**
Kasavin: "There's nothing more frustrating ... you just hit a difficulty wall ... So we try to build systems into our games that mitigate those kinds of moments." Giovannetti: replayability is "off the charts", and "the important thing is to quickly allow the player to start carving out new strategies".
*Why it matters:* Minimise time from loss to the next run's first decision; make the loss screen point at an untried strategy.
Sources: [S8], [S3].

**4.8 Be more afraid of boring players than challenging them.**
Rosewater lesson 16: "people fear challenging the players more than boring them, but I think that's backward ... The greatest risk is not taking risks."
*Why it matters:* Boss rules should dare, not just add a number.
Sources: [S28].

**4.9 Tension with the sawtooth: players want progress to feel constant even if difficulty oscillates.**
Meier (as reported): "You cannot reward and reflect progress too much in a game", and players do not want the peaks and valleys of real history. This is about progress feedback, not difficulty, so the two can coexist: oscillate difficulty, keep progress feedback steady.
*Why it matters:* Make progress visible within a heat even when the heat is a "valley".
Sources: [S11].

---

## 5. Systems and economy design

**5.1 Positive feedback magnifies early success; negative feedback stabilises and prolongs.**
Per Dormans (summarising LeBlanc 1999, Salen and Zimmerman 2004): Monopoly-style positive loops "drive the game to a conclusion and magnif[y] early successes"; negative loops (rubber-banding) diminish differences.
*Why it matters:* The mult-scaling stack is a positive loop. Decide where the negative loops (boss rules, targets, move budget) bite so runs do not snowball or become decided at heat 3.
Sources: [S22].

**5.2 One loop is not enough: pair an engine with friction.**
Dormans: "one feedback loop is generally not enough to create an interesting dynamic mechanic". The "dynamic engine" (invest to raise output) needs "dynamic friction" (something that consumes output), so players balance several tasks. Simulate with Machinations.
*Why it matters:* Your engine is the stack; friction is boss rules, target ramp and the move budget. Check the player always has at least three things to balance.
Sources: [S22], [S39] (L).

**5.3 Value chains: a resource has value only through what it enables, ending in a motivational anchor.**
Daniel Cook: "Value for a particular action comes from how it facilitates subsequent activities." Chains must end in an intrinsically rewarding anchor; a broken chain shows up as player comments like "X seems pointless", "I didn't even notice X". Balance rule: "exponentially increasing sources should be matched by exponentially increasing costs on sinks."
*Why it matters:* Audit money: what does each coin buy, what is the anchor, and does late-run income outgrow shop sinks (money going dead)?
Sources: [S40].

**5.4 Emergence vs progression is a design axis; most games mix them.**
Juul (2002): emergence is simple rules giving many outcomes; progression is designed challenges in sequence. Dormans proposes integrating them through feedback loops.
*Why it matters:* Chip synergies are emergence; heats, championships and boss rules are progression. Keep the progression authored and the emergence free.
Sources: [S22], [S41] (B).

**5.5 Balance has two basic kinds: transitive (cost curves) and intransitive (counters).**
Schreiber and Romero's *Game Balance* has separate chapters for "Transitive Mechanics and Cost Curves" and "Intransitive Mechanics and Payoff Matrices", plus "Economic Systems", "Situational Balance", "Progression in PvE Games" and "Analytics" (table of contents read; chapters not). Jaffe et al.'s AIIDE 2012 paper on "restricted play" is the academic precedent for bot-based balance evaluation (title and venue only).
*Why it matters:* Chips fit cost curves against shop price; boss rules are intransitive counters to archetypes; bot comparisons are a recognised method.
Sources: [S13] (L), [S42] (B).

**5.6 Metrics inform, they do not decide.**
Mega Crit built an in-house tool that logged every playtest game, so they could chart pick rates and test complaints against data, and Giovannetti warned that metrics can mislead if not interpreted carefully (from the GDC 2019 preview and secondhand summaries).
*Why it matters:* Pick rate and win rate are confounded by when an option is offered. Compare like for like (your paired-seed approach).
Sources: [S43] (L/S).

---

## 6. Accessibility

**6.1 Start with the four most-complained-about issues and the basics.**
GAG Basic names them as remapping, text size, colour-blindness and subtitle presentation, and lists: "ensure no essential information is conveyed by a fixed colour alone", "provide high contrast between text/UI and background", "use an easily readable default font size", "ensure that all settings are saved", "offer a wide choice of difficulty levels", "include an option to adjust the game speed".
*Why it matters:* A checkers board with two board colours and coloured chips is a colour-reliance hazard. Chips and coups need shape or icon channels as well as colour.
Sources: [S18].

**6.2 Provide a second channel for every cue.**
XAG 103 requires key visual and audio cues to be expressed through multiple sensory methods; GAG Basic says "ensure no essential information is conveyed by sounds alone".
*Why it matters:* Scoring sounds must have a visual twin and the reverse.
Sources: [S17], [S18].

**6.3 Reversibility and confirmation before destructive actions.**
XAG 115: players need to "identify and correct any player-input errors before permanent or destructive action takes place".
*Why it matters:* Selling a chip, ending a heat and spending the last coin need confirmation, and undo within a heat is the better fix.
Sources: [S17].

**6.4 Use APX patterns as a design vocabulary: design for barriers, not disabilities.**
APX has 12 Access patterns (Second Channel, Clear Text, Distinguish This From That, Do More With Less, Personal Interface, Flexible Controllers and others) and 10 Challenge patterns: Moderation In All Things, House Rules, Bypass, Undo Redo, Helping Hand, Training Ground, Play Alongside, Slow It Down, Total Recall, Save Early Save Often. The site says the aim is "adding flexibility to challenge", not removing challenge.
*Why it matters:* "House Rules", "Undo Redo", "Total Recall" (review what happened), "Slow It Down" and "Training Ground" map straight onto your own house rules, move history and a practice mode.
Sources: [S44].

**6.5 Time pressure and motion are accessibility axes.**
XAG 116 covers UI time limits (not core gameplay timers). GAG Advanced: "do not make precise timing essential to gameplay". GAG Intermediate: provide the option to turn off or hide background movement.
*Why it matters:* Keep decisions untimed; offer a flat-background option.
Sources: [S17], [S18].

**6.6 Include impaired players in playtests.**
GAG Advanced: "include every relevant category of impairment ... amongst play-testing participants, in representative numbers".
*Why it matters:* Costs little; catches colour and cognitive-load issues early.
Sources: [S18].

---

## 7. Process: iteration, playtesting, metrics, prototyping, models

**7.1 Players diagnose well and prescribe badly.**
Rosewater lesson 19: players "are excellent at identifying problems, but they're not as equipped to solve the problems"; use them to find what is wrong "but take it with a grain of salt when they offer you solutions". Cook's value-chain essay reads the same way: "X is boring / pointless / I don't understand why I'm playing" are structural signals about the economy.
*Why it matters:* Triage playtest notes into symptom (keep) and proposed fix (discount), then look for the structural cause.
Sources: [S28], [S40].

**7.2 Prototype to find constraints, then enforce them.**
Rosewater lesson 18: "restrictions aren't an obstacle but rather a valuable tool". Examples found: Balatro's 20-word cap [S5]; Into the Breach's 8x8 grid, which made hand-authoring cheaper than procedural generation [S36].
*Why it matters:* Pick explicit constraints (words per chip, effects per chip, board size) and treat violations as bugs.
Sources: [S28], [S5], [S36].

**7.3 Cull hard.**
Giovannetti: "brainstorm thousands of different card designs and cut out the chaff down to the designs that we felt had the most impact", then "rigorous and extensive playtesting". LocalThunk: sometimes "an effect will just be completely cut".
*Why it matters:* The content budget is for the survivors; the backlog of chips is allowed to be shorter than the idea list.
Sources: [S3], [S5].

**7.4 Loops versus arcs (Daniel Cook).**
Loops: "mental model, action, system, feedback, updated model", repeated, building holistic "wisdom"; arcs are one-shot payloads whose repeat value drops, and chaining arcs leads to the "content treadmill". Ask "what repeats and what doesn't?"
*Why it matters:* The run is a loop (good); authored story or unlock-reveal beats are arcs. Do not rely on arcs for retention.
Sources: [S45].

**7.5 Keep a fresh-eyes check in the process.**
Into the Breach's team could not see their own telegraph problem until others played it [S20]. The Games User Research literature (Drachen, Mirza-Babaei and Nacke, OUP 2018) and Hodent's UX work are the standard references for structured methods (bibliographic records only).
*Why it matters:* Schedule fresh-eyes sessions per milestone, not per release.
Sources: [S20], [S46] (B), [S47] (B).

**7.6 MDA has critics and successors; know what URF's lens inherits.**
URF's 8 Kinds of Fun is MDA's "Aesthetics". Walk, Görlich and Barrett's DDE (2017) renames Mechanics to Design, Dynamics to Dynamics, Aesthetics to Experience, and responds to criticism that MDA is mechanics-heavy and under-serves narrative (that description is from a secondary summary; I read only the record).
*Why it matters:* Low priority. MDA is fine for a mechanics-driven game; DDE matters if narrative or meta layers grow.
Sources: [S48] (B/S).

**7.7 Design for emotion explicitly.**
Rosewater lesson 5: "Don't confuse 'interesting' with 'fun'": intellectual versus emotional stimulation, and emotional satisfaction "runs deeper". Lesson 6: decide what emotion the game is trying to evoke.
*Why it matters:* Chips can be interesting to read yet unfun to play. The test is the feeling when the score tallies.
Sources: [S28].

---

## 8. Ethics and dark patterns (as relevant to a premium single-player roguelike)

**8.1 A dark game design pattern is deliberate harm.**
Zagal, Björk and Lewis (FDG 2013): "a pattern used intentionally by a game creator to cause negative experiences for players which are against their best interests and likely to happen without their consent". Categories: temporal (grinding, playing by appointment), monetary (pay to skip), social (social pyramid schemes). Context changes the darkness; an optional appointment mechanic that does not block progression is much less dark.
*Why it matters:* Use as a review checklist for unlock tracks, daily seeds and any streak mechanic.
Sources: [S49].

**8.2 Grinding is coercive when it gates content.**
The same paper: grinding is paired in practice with "pay to skip", meaning players pay to skip the grind.
*Why it matters:* Premium pricing means no reason to gate content behind repetition; unlock by play variety instead.
Sources: [S49].

**8.3 Random rewards for real money are psychologically akin to gambling.**
Drummond and Sauer (Nature Human Behaviour, 2018) argue loot boxes in video games are psychologically akin to gambling; King, Delfabbro and Griffiths (2010) categorise game structural characteristics that facilitate excessive play (title and venue verified; content not read).
*Why it matters:* Randomised shop offers are fine because they cost in-game money only. Keep it that way and avoid slot-machine presentation language.
Sources: [S50] (B), [S51] (B).

**8.4 A shipped precedent: the Balatro developer's explicit stance.**
LocalThunk: "I don't want to put gambling in my game. There's no way that you can spend extra money in Balatro", and "ethically I wouldn't ever be comfortable putting that in". Some storefronts pulled the game because it "looks like Poker". A podcast episode covers steps to ensure the game is never conflated with gambling (listing only).
*Why it matters:* Rating and storefront risk comes from presentation (suits, chips, slot-like language), not only mechanics.
Sources: [S5], [S52] (L).

**8.5 Understanding reward schedules is not neutral.**
Hopson explains that avoidance schedules ("work to keep things from happening", e.g. houses that decay unless visited) are "a relatively cheap strategy" for developers and create "behavioral momentum".
*Why it matters:* Avoid decaying-streak mechanics; it is the same technique, whatever the intent.
Sources: [S30], [S49].

**8.6 Respect the player's time and the design contract.**
Meier (as reported): designers and players each can "destroy" the experience, and designers must "value the player's time".
*Why it matters:* Cap run length, skip animations on request, and keep restarts fast.
Sources: [S11].

---

## Where this extends or contradicts the URF Academy lens

**Extends (new territory):**
- **Randomness taxonomy and fairness perception.** URF has no treatment of input vs output randomness, odds display or perceived fairness. This is the biggest gap for a generated-board game.
- **Systems and economy.** Sources and sinks, feedback loops, engine plus friction, value chains. URF's "core loops" is about experience cadence; these are about quantity flows and balance.
- **Interesting decisions and dominant strategies.** URF's depth/breadth/elegance is aesthetic; Meier, Dormans and Ma give testable audits.
- **Clarity as a hard constraint that deletes content** (Into the Breach), well beyond "complexity is a cost".
- **Empirical motivation models.** LeBlanc's 8 Kinds is a designer taxonomy; SDT (experimentally tested) and Quantic Foundry (factor analysis of over a million players) are measured; Rosewater's psychographics (Timmy/Johnny/Spike) fit deckbuilders directly.
- **Accessibility, ethics, telemetry:** not in URF at all.
- **Rosewater's other lessons.** URF's resonance and piggybacking are Rosewater lessons 3 and 4. The remaining 18 (e.g. 5, 13, 16, 18, 19) are unused.

**Contradicts or complicates:**
- **Flow and the sawtooth curve.** Valve's Director adjusts frequency, not amplitude ("pacing, not difficulty"); Meier reports players want constant visible progress rather than peaks and valleys (a progress-feedback claim, not a difficulty one); Celeste and XAG 108 argue the player, not the designer's curve, should set the level, and that this can be changed at any time. Treat the sawtooth as a default pacing tool, not the whole difficulty strategy.
- **Complexity as a cost versus depth.** Dormans says one loop "is generally not enough"; Ma wants priorities to shift ("it's not much of a game" otherwise). Elegance means few concepts producing interacting loops, not few parts.
- **"Listen to the players" in playtest feedback.** Rosewater lesson 19: take symptoms, discount prescriptions.
- **Paper prototyping.** For a system with generated content and bots, simulation and data (Giovannetti; Jaffe's restricted play) displace paper for balance, though not for first-impression clarity tests.
- **Interesting vs fun.** Rosewater lesson 5 warns that the "depth" lens can bias toward intellectual interest over emotional payoff.
- **Core-loop satisfaction versus value chains.** Cook found a loop can be dull yet valued through its place in a chain; and a "fun" loop with no chain goes dead.
- **Conventional randomness wisdom.** Zhang et al. (single small study) found input randomness reduced satisfaction in a card game, against the folk rule. The finding is weak but a reason to test generation, not assume it.

---

## Top 10 additions for the skill (ranked by value)

1. **Randomness taxonomy and fairness audit.** Classify each random element as input or output, band input-randomness difficulty so spread (not mean) is controlled, make odds visible, prefer streak-limited randomness, and playtest the "folk rule" rather than assume it. (Burgun, Engelstein, Zhang et al., Meier/Pardo, Valve)
2. **Clarity as a deletion rule.** If an effect cannot be shown in a short animated preview, cut or redesign it; a text budget (Balatro: four lines, 20 words); telegraph consequences; test on fresh eyes; keep one unmistakable top-level gauge. (Ma/Davis, LocalThunk)
3. **Interesting-decision and dominant-strategy audit.** Test whether one build or heuristic always wins; make the optimal line the fun line; no even scaling of both sides; guarantee "more than one meaningful option" in generated content. (Meier, Dormans, Rosewater #13, Ma, Giovannetti)
4. **Economy as faucets, drains and growth-matching.** Write value chains to a motivational anchor, match source growth to sink growth, pair every engine with friction, and read "X feels pointless" as a broken chain. (Cook, Dormans, Schreiber and Romero)
5. **Synergy as a goal, with counter-pressure.** Strong combos are good in single-player; guard with varied boss rules, "cannibalises neighbours / never taken" as the two failure tests, tune by single numeric knobs, and tag chips by psychographic (Timmy/Johnny/Spike). (Giovannetti, LocalThunk, Rosewater)
6. **Failure and difficulty as autonomy.** Fail-forward (fast restart, carried knowledge, difficulty-wall mitigation); player-set, non-judgemental, changeable difficulty (Celeste, XAG 108); frame harder stakes as added rules, not removed rewards (Hopson, Pardo).
7. **Accessibility baseline.** Never colour alone, second channels for cues, readable text, undo/confirm destructive actions, game-speed and reduced-motion options, untimed decisions, APX challenge patterns as vocabulary. (GAG, XAG, APX)
8. **Juice with restraint.** Maximum output for minimum input, feedback that carries information, designed as a layer with off/fast-forward controls. (Jonasson/Purho, Swink, Nijman, XAG 117)
9. **Motivation audit.** Check each feature against competence/autonomy/relatedness and the Quantic Foundry motivations; accept relatedness comes from seeds and sharing; ownership and discovery as attachment drivers. (Ryan et al., Quantic Foundry, Rosewater)
10. **Feedback and data process.** Players diagnose, designers prescribe; metrics inform but mislead (compare like for like); cull hard; use restrictions on purpose; keep fresh-eyes testing per milestone. (Rosewater #18/#19, Giovannetti, Ma)

Honourable mentions (not in the ten): dark-pattern and reward-schedule checklist for a premium game (Zagal et al., Hopson, Drummond and Sauer, LocalThunk); loops-versus-arcs analysis (Cook); peak-end and endowment effects for the cash-out and sell screens (Kahneman et al., by analogy).

---

## Sources

Format: [ID] status. Author, title, venue, year. URL.

**Randomness and roguelike/deckbuilder**
- [S1] P. Zhang, Monteiro, Liang, Ma, Baghaei. "Effect of Input-output Randomness on Gameplay Satisfaction in Collectable Card Games." 2021 IEEE Conference on Games (CoG); arXiv:2107.08437. https://arxiv.org/abs/2107.08437 ; DOI 10.1109/CoG52621.2021.9619020 (DOI record verified via Crossref).
- [S2] P. Burgun. "Randomness and Game Design." Gamasutra/Game Developer, 15 Oct 2014. https://www.gamedeveloper.com/design/randomness-and-game-design
- [S3] P. Couture (interviewer). "Road to the IGF: Mega Crit Games' Slay the Spire" (Anthony Giovannetti). Game Developer, 22 Jan 2020. https://www.gamedeveloper.com/disciplines/road-to-the-igf-mega-crit-games-i-slay-the-spire-i-
- [S4] P. Holmes. "Balatro Interview - LocalThunk on an 'indie take on solitaire with a poker coat of paint'." Rogueliker, 7 Mar 2024. https://rogueliker.com/balatro-interview/
- [S5] P. Stewart. "Balatro Was Almost Called Joker Poker And Other Details From Its Creator." Game Informer, 21 Mar 2024. https://gameinformer.com/interview/2024/03/21/balatro-was-almost-called-joker-poker-and-other-details-from-its-creator
- [S6] P (slides). Booth. "The AI Systems of Left 4 Dead." Valve, AIIDE 2009 keynote. https://steamcdn-a.akamaihd.net/apps/valve/2009/ai_systems_of_l4d_mike_booth.pdf
- [S7] P. "Berlin Interpretation." RogueBasin; International Roguelike Development Conference 2008, posted 16 Sep 2008. https://www.roguebasin.com/index.php/Berlin_Interpretation
- [S8] P. Graft. "Roguelikes and narrative design with Hades creative director Greg Kasavin" (GDC Podcast ep. 16). Game Developer, 28 Jan 2021. https://www.gamedeveloper.com/design/roguelikes-and-narrative-design-with-i-hades-i-creative-director-greg-kasavin
- [S9] L. Kasavin and Korb, "Breathing Life into Greek Myth: The Dialogue of Hades", GDC 2021 (listing only). https://gdcvault.com/play/1026975/Breathing-Life-into-Greek-Myth
- [S10] L. Engelstein. "White, Brown, and Pink: The Flavors of Tabletop Game Randomness." GDC 2018 (Board Game Design Day). https://gdcvault.com/play/1024920/Board-Game-Design-Day-White ; write-up: https://gamedeveloper.com/design/video-how-to-utilize-different-types-of-game-randomness (P, listing text only).
- [S11] P. Graft. "GDC: Sid Meier's Lessons On Gamer Psychology" ("The Psychology of Game Design (Everything You Know Is Wrong)", GDC 2010 keynote). Game Developer, 12 Mar 2010. https://www.gamedeveloper.com/game-platforms/gdc-sid-meier-s-lessons-on-gamer-psychology (talk: https://gdcvault.com/play/1012186/The-Psychology-of-Game-Design, L).
- [S12] S (news write-up, read). Leahy. "Sid Meier and Rob Pardo on Probability and Player Psychology." Shacknews, 15 Mar 2010. https://www.shacknews.com/article/62807/sid-meier-and-rob-pardo

**Juice, feel, clarity**
- [S13] L. Schreiber and Romero. *Game Balance.* CRC Press, 2021 (publisher page and table of contents read). https://www.routledge.com/Game-Balance/Schreiber-Romero/p/book/9781498799577
- [S14] L. Swink. *Game Feel: A Game Designer's Guide to Virtual Sensation.* CRC Press/Morgan Kaufmann, 2009 (publisher description read). https://www.routledge.com/Game-Feel-A-Game-Designers-Guide-to-Virtual-Sensation/Swink/p/book/9780123743282
- [S15] P (write-up). "Video: Is your game 'juicy' enough?" (Jonasson and Purho, GDC Europe 2013). Game Developer, 23 Aug 2013. https://www.gamedeveloper.com/design/video-is-your-game-juicy-enough-
- [S16] L. Nijman (Vlambeer). "The Art of Screenshake." INDIGO Classes 2013. https://www.youtube.com/watch?v=AJdEqssNZ-U (title verified via oEmbed; content not viewed).
- [S17] P. Microsoft. Xbox Accessibility Guidelines (XAG 103, 108, 115, 116, 117, 123). https://learn.microsoft.com/en-us/gaming/accessibility/guidelines (individual pages: .../xbox-accessibility-guidelines/108 etc.).
- [S18] P. Game Accessibility Guidelines (Basic, Intermediate, Advanced). https://gameaccessibilityguidelines.com/basic/ ; .../intermediate/ ; .../advanced/
- [S19] P. Wawro. "Into the Breach dev on UI design: 'Sacrifice cool ideas for the sake of clarity every time'." Game Developer, 5 Mar 2018. https://www.gamedeveloper.com/design/-i-into-the-breach-i-dev-on-ui-design-sacrifice-cool-ideas-for-the-sake-of-clarity-every-time-
- [S20] P. Wawro (as S19), plus Davis' GDC 2019 talk "'Into the Breach' Design Postmortem" (L, https://gdcvault.com/play/1026333/-Into-the-Breach-Design).
- [S21] P. Rosewater. "Timmy, Johnny, and Spike." Making Magic, 2002 (reprints 2013). https://magic.wizards.com/en/news/making-magic/timmy-johnny-and-spike
- [S22] P. Dormans. "Integrating Emergence and Progression." DiGRA 2011. https://dl.digra.org/index.php/dl/article/download/593/593/590 ; DOI 10.26503/dl.v2011i1.593
- [S23] L. Salen and Zimmerman. *Rules of Play: Game Design Fundamentals.* MIT Press, 2004 (cited by [S22]; not fetched; the "discernable and integrated" claim is from my knowledge of the book).

**Psychology**
- [S24] P. Ryan, Rigby, Przybylski. "The Motivational Pull of Video Games: A Self-Determination Theory Approach." *Motivation and Emotion* 30(4), 347-363, 2006. DOI 10.1007/s11031-006-9051-8 (full PDF read).
- [S25] B. Przybylski, Rigby, Ryan. "A Motivational Model of Video Game Engagement." *Review of General Psychology* 14(2), 154-166, 2010. DOI 10.1037/a0019440
- [S26] P. Quantic Foundry. *Gamer Motivation Model Reference* (2019). https://quanticfoundry.com/wp-content/uploads/2019/04/Gamer-Motivation-Model-Reference.pdf (site pages themselves returned 403).
- [S27] B. Yee and Ducheneaut. "Gamer motivation profiling: uses and applications." In Drachen, Mirza-Babaei, Nacke (eds.), *Games User Research*, OUP, 2018. DOI 10.1093/oso/9780198794844.003.0028
- [S28] P. Rosewater. "Twenty Years, Twenty Lessons" Parts 1-3. Making Magic, 30 May, 6 Jun, 13 Jun 2016 (GDC 2016 talk). https://magic.wizards.com/en/news/making-magic/twenty-years-twenty-lessons-part-1-2016-05-30 ; ...part-2-2016-06-06 ; ...part-3-2016-06-13
- [S29] B. Kahneman and Tversky. "Prospect Theory: An Analysis of Decision under Risk." *Econometrica* 47(2), 263-291, 1979. DOI 10.2307/1914185
- [S30] P. Hopson. "Behavioral Game Design." Gamasutra/Game Developer, 27 Apr 2001. https://www.gamedeveloper.com/design/behavioral-game-design
- [S31] B. Kahneman, Knetsch, Thaler. "Experimental Tests of the Endowment Effect and the Coase Theorem." *Journal of Political Economy* 98(6), 1990 (Crossref record found as a reprint chapter, DOI 10.2307/j.ctvcm4j8j.7).
- [S32] B. Kahneman, Fredrickson, Schreiber, Redelmeier. "When More Pain Is Preferred to Less: Adding a Better End." *Psychological Science* 4(6), 1993. DOI 10.1111/j.1467-9280.1993.tb00589.x
- [S33] B. Sweller. "Cognitive Load During Problem Solving: Effects on Learning." *Cognitive Science* 12(2), 1988. DOI 10.1207/s15516709cog1202_4
- [S34] S. Hodent. *The Gamer's Brain: How Neuroscience and UX Can Impact Video Game Design.* CRC Press, 2017 (retail listings only; also Isbister and Hodent, *Game Usability*, CRC Press 2022, DOI 10.1201/9781003109389, B).

**Difficulty, fairness, decisions**
- [S35] L. Meier. "Interesting Decisions." GDC 2012. Write-up (P): Francis, "Video: Sid Meier explores 'interesting decisions' in gameplay", Game Developer, 27 Sep 2018. https://www.gamedeveloper.com/design/video-sid-meier-explores-interesting-decisions-in-gameplay
- [S36] P. Wiltshire. "Reimagining failure in strategy game design in Into the Breach." Game Developer, 28 Feb 2018. https://www.gamedeveloper.com/design/reimagining-failure-in-strategy-game-design-in-i-into-the-breach-i-
- [S37] L/S. Hunicke and Chapman. "AI for Dynamic Difficulty Adjustment in Games." AAAI Challenges in Game AI Workshop, 2004; Hunicke, "The Case for Dynamic Difficulty Adjustment in Games," ACE 2005, DOI 10.1145/1178477.1178573. Abstract seen only through search snippets; the Northwestern PDF host was unreachable.
- [S38] P. "Celeste's Assist Mode" (Vice). https://www.vice.com/en/article/d3w887/celeste-difficulty-assist-mode (Thorson quotes).

**Systems and economy**
- [S39] L. Adams and Dormans. *Game Mechanics: Advanced Game Design.* New Riders, 2012; Machinations tool: https://machinations.io/ (site reachable; book description via search only).
- [S40] P. Cook. "Value chains - A method for creating and balancing faucet-and-drain game economies." Lostgarden, 12 Dec 2021. https://lostgarden.com/2021/12/12/value-chains/
- [S41] B. Juul. "The Open and the Closed: Games of Emergence and Games of Progression." Computer Games and Digital Cultures, 2002 (DiGRA record). DOI 10.26503/dl.v2002i1.9 (site unreachable; claim via [S22]).
- [S42] B. Jaffe, Miller, Andersen, Liu, Karlin, Popovic. "Evaluating Competitive Game Balance with Restricted Play." AIIDE 2012. DOI 10.1609/aiide.v8i1.12513
- [S43] L/S. Giovannetti. "Slay the Spire: Metrics Driven Design and Balance." GDC 2019. Preview (P): https://www.gamedeveloper.com/design/learn-i-slay-the-spire-i-s-metrics-driven-approach-to-game-balancing-at-gdc-2019 ; video https://www.youtube.com/watch?v=7rqfbvnO_H0 (title verified; not viewed). The "metrics can mislead" caveat is from secondhand summaries.

**Accessibility, process, ethics**
- [S44] P. AbleGamers. Accessible Player Experiences (APX). https://accessible.games/accessible-player-experiences/
- [S45] P. Cook. "Loops and Arcs." Lostgarden, 30 Apr 2012. https://lostgarden.com/2012/04/30/loops-and-arcs/
- [S46] B. Drachen, Mirza-Babaei, Nacke (eds.). *Games User Research.* OUP, 2018 (chapter records via Crossref).
- [S47] B. Drachen, El-Nasr, Canossa et al. *Game Analytics: Maximizing the Value of Player Data.* Springer, 2013. DOI 10.1007/978-1-4471-4769-5
- [S48] B/S. Walk, Görlich, Barrett. "Design, Dynamics, Experience (DDE): An Advancement of the MDA Framework for Game Design." In *Game Dynamics*, Springer, 2017. DOI 10.1007/978-3-319-53088-8_3 (description is secondhand).
- [S49] P. Zagal, Björk, Lewis. "Dark Patterns in the Design of Games." FDG 2013. https://gup.ub.gu.se/file/101018 (full text read; Chalmers record: https://research.chalmers.se/en/publication/177148).
- [S50] B. Drummond and Sauer. "Video game loot boxes are psychologically akin to gambling." *Nature Human Behaviour* 2, 530-532, 2018. DOI 10.1038/s41562-018-0360-1
- [S51] B. King, Delfabbro, Griffiths. "Video Game Structural Characteristics: A New Psychological Taxonomy." *Int. J. Mental Health and Addiction* 8, 2010 (online 2009). DOI 10.1007/s11469-009-9206-4
- [S52] L. Game Maker's Notebook. "Balatro Creator LocalThunk Talks Inspirations and Jokers." 9 Dec 2024 (episode description only). https://gamemakersnotebook.libsyn.com/balatro-creator-localthunk-talks-inspirations-and-jokers

**Other sources seen but not relied on:** Mark Brown, "The Two Types of Random in Game Design" (GMTK, 2020; https://www.youtube.com/watch?v=dwI5b-wRLic, title verified, cited only through S1); Koster, *A Theory of Fun* (cited through Burgun, S2, not fetched); Schell, *The Art of Game Design* 3rd ed. (CRC Press, record verified, https://www.routledge.com/The-Art-of-Game-Design-A-Book-of-Lenses/Schell/p/book/9781138632059; no claims drawn); Fullerton, Sylvester, Engelstein and Shalev (not drawn on).

Dropped for weak sourcing: AI-generated or fan summaries of the Slay the Spire talk, a third-party GitHub project that re-implemented its metrics, forum/listicle claims about meta-progression, Medium posts about Dead Cells and Into the Breach.
