# QA Flags — Remaining Ten Pilot Cards (v0.4 pattern)

Companion to `cards-remaining-v0.4.json`. Every ambiguity, count convention,
and transcript/extraction discrepancy flagged during the build, per episode.
Nothing below was silently resolved: where two numbers or readings exist,
both are recorded in the card and the conflict is listed here. Submitter
names/locations are excluded from the cards entirely (per the pilot
pattern); garbled-name flags are noted only where they bear on QA.

Cross-checks performed for this build: each episode's extraction record was
spot-checked against the raw tail transcript (checkpoints, reveal lines, and
disputed answers all re-verified in the transcript text on 2026-10-14). No
extraction/transcript disagreements were found beyond the items already
flagged in EXTRACTION-NOTES.md and repeated here.

## Global conventions applied (same as the passed 862/863 cards)

- `charged_turns` = turns in the questions phase (yes/no questions + any
  in-phase title guesses). The reserved final guess is tracked separately in
  `final_guess_status`, never folded into `charged_turns`.
- SUPERSEDED 2026-10-14 (Dot QA rounds 1–2; see "Dot QA cleanup applied
  2026-10-14" and "Dot QA round-2 cleanup applied 2026-10-14" below): the
  prose-string option in this bullet was retired — unauditable split fields
  are now actual JSON `null`, with the explanation carried in the round's
  notes (`count_convention` / `evidence_completeness`). Original text: Where
  a full-round yes/no vs title-guess split is not auditable (pre-tail
  questions, fuzzy counts), the fields are `null` or an explicit
  "identifiable vs host-counted" string — never a guessed integer.
- Host answers that conflict with sourced facts stay in
  `round_history_traits` (playable: false) with the conflict noted; the
  sourced position goes in `playable_traits`. Host answers are never
  overwritten in the history record.
- Equivocal host answers ("I don't think so", "I think so") are recorded as
  equivocal/unknown, not rounded to yes or no.

## Ep 864 — Apex Legends (gs20q-864)

- **Count is the show's fuzzy number, not an enumeration.** Charged turns
  recorded as 21 per the host's on-air call ("let's just call it 21
  questions this week", 4772.05s). An early license answer by the answerer
  was recanted and four questions were rewound; which questions the rewind
  voided is not recoverable. Yes/no vs title-guess split is `null`.
- **The round's pivotal fact is a definition question.** Apex is set in the
  Titanfall universe (an original game series), which is not an external
  license — the card's playable trait states this explicitly because the
  recanted answer turned on it.
- **"On a Nintendo platform? Yes"** is true only via the 2021 Switch port;
  flagged in the trait note.
- Tail begins mid-round; ledger is partial by design (checkpoints + notable
  Q&A only, no fabricated full ledger).

## Ep 865 — Palworld (gs20q-865)

- **Title garble (not silently fixed):** Whisper renders the game
  "power world"/"power" throughout the tail. Identification as Palworld is
  confirmed in-transcript (developer Pocketpair named post-round,
  4738.49s). The card carries `as_transcribed_in_tail`.
- **Questions 16–19 only partially identifiable** (loose phrasing; the
  positive-reviews answer was given "for free"). Checkpoints (15 at
  4236.41s; 19 used at 4338.10s) + final question fix the total at 20.
  Split fields are `null` with a `split_confidence` note.
- **"Action" answer was generous** (host: "very wide umbrella of action") —
  same predicate problem as Forza's "action game?" in ep 863; the round
  trait carries the caveat and the playable traits use only the sourced
  genre labels (survival / monster-taming).
- **Release-state nuance:** at air date (2026-07-17) the game had just left
  early access (full release 10 July 2026 per Wikipedia). Scope lists both
  the early-access (Jan 2024) and full-release dates.
- Solve was collective; no individual solver credited in the transcript.

## Ep 866 — 24: The Game (gs20q-866)

- **Count convention conflict (both recorded):** host-checkpoint total 20
  vs 19 individually distinct questions (delegated cross-check). Question
  #17 is not individually identifiable; the opening platform cluster is
  garbled (3752.58–3757.24s), so pre-10 counting rests on host tallies.
- SUPERSEDED 2026-10-14 (Dot QA round-1 cleanup; see the cleanup sections
  below): the combined playable trait described in this bullet was split —
  "Counterterrorism-themed" = true, "Military/espionage (broader
  predicate)" = Unknown. Original flag text: **Disputed answer — the
  round's known fault line:** "Espionage or military combat? No" (3918.13s)
  was disputed on air ("send this up to the commission", 4207.20s); 24 is a
  counterterrorism/espionage property. The history trait records the answer
  as given; the playable trait records the sourced position
  (espionage/counterterrorism-themed: true) with an explicit instruction
  not to reuse the round's No.
- **Publisher is region-split** (Sony Computer Entertainment EU / 2K NA) —
  an "Published by Sony?" predicate in play needs the region caveat; the
  host's reveal called it "made by Sony" (developer SCEE Cambridge Studio).
- Team declined the final guess and asked for the reveal — recorded as
  `available_but_declined`, not as a used guess.

## Ep 867 — Detroit: Become Human (gs20q-867)

- Cleanest card of the ten: full round in-tail, checkpoints 5/10/15 match
  the enumeration exactly, full ledger embedded. No count flags.
- **"Multi-platform? Yes" is time-dependent:** host answered "It is today"
  (PS4 exclusive at 2018 launch; Windows port Dec 2019). Trait note carries
  the launch-vs-now distinction.
- **"Published by Sony? Yes"** is edition-dependent in the same way: SIE
  published the PS4 edition; Quantic Dream self-published the Windows
  edition. Recorded in the facts block.
- Solver not individually named (team-voiced finish) — recorded as such.

## Ep 869 — Fall Guys (gs20q-869)

- **Count convention conflict (both recorded):** host-checkpoint total of
  20 questions + final guess vs 19 individually distinct questions + guess
  (delegated cross-check). Question #17 is not cleanly identifiable;
  candidate is a repeated "Is there combat?" probe (3441.45s / 3505.09s)
  with no transcribed answer — the ledger slot is marked `unknown` rather
  than filled.
- SUPERSEDED 2026-10-14 (Dot QA round-1 cleanup; see the cleanup sections
  below): the Switch game-card rationale was removed from the card; the
  host's "Yes" stays in round history and the underlying predicate is now
  marked Unknown per sources. Original flag text: **"Cartridge-based? Yes"
  (Q5)** rests on the Switch game-card format; the original 2020
  PS4/Windows release is disc/download. Recorded as answered, with the
  caveat in the trait note.
- **"On a Nintendo platform? Yes"** is true only via the 2022 Switch
  release — flagged.
- **"Indie? Yes"** is as-answered; Mediatonic was independent at the 2020
  launch and Epic-owned by the 2022 relaunch. Round history only.
- **"Play as a human? No"** was the round's pivotal (and confusing) answer;
  host's steering aside is quoted in the trait note. Playable traits avoid
  the character-form predicate entirely (no sourced trait asserts it).
- Title/scope: launched as *Fall Guys: Ultimate Knockout* (2020), shortened
  to *Fall Guys* at the 2022 free-to-play relaunch; both titles accepted.

## Ep 870 — Overlord (gs20q-870)

- **Count convention conflict (both recorded):** host-tally-implied total
  20 vs 18 individually distinct questions (delegated cross-check). One
  question predates the tail (host correction: "Say that it was 10, sorry",
  4107.94s); one question between Q17 and the 18-used checkpoint is not
  cleanly identifiable (possibly the disputed "on a Nintendo platform
  ever" ask argued at 4292.88s). The host's "that's 15" (4218.63s) lands on
  the 14th distinct question — the ledger flags this inline.
- **Genre answer conflicts with sources:** host answered No to the compound
  "driving/strategy/platformer?" (4169.28s), but Wikipedia describes
  RTS elements (minion control) and classifies the game as action
  role-playing. The team swept every genre and missed partly on this.
  Playable trait records the sourced position; history trait records the
  answer with a DISPUTED note. Not resolved either way.
- **Platform/date imprecision in the reveal:** host called it a "2007 Xbox
  360/PS3 game"; the PS3 version actually shipped in 2008 (as Raising
  Hell). Scope and facts state the sourced dates.
- Segment start in the extraction is the in-tail resumption point; the
  round's intro and ~1 question predate the tail by design.

## Ep 871 — Where's Waldo? (gs20q-871)

- SUPERSEDED 2026-10-14 (Dot QA round-2 cleanup; see "Dot QA round-2
  cleanup applied 2026-10-14" below): the ledger was restructured into
  individually observed entries with unsupported indices set to null, and
  the "evidently not counted" claim below is withdrawn — the probe's
  counted status is unresolved. Original flag text: **Uncounted probe:**
  between the 11- and 15-checkpoints, four candidate questions are visible
  but only three net counted. The equivocally answered "Is it a pixel hunt
  game?" probe (4476.76s) was evidently not counted and is listed under
  `not_counted`. The ledger's 12–14 slots are therefore a compressed
  representation (flagged in the ledger itself) — QA may prefer a different
  presentation of this window.
- **Solver unattributable:** two hosts arrived "literally the exact same
  frame" (4511.92s); no individual solver recorded.
- **Release-month discrepancy in sources:** Wikipedia infobox says July
  1991; some listings say September 1991. Card records 1991 with both
  months noted; the year (the only round-relevant fact) is not in dispute.
- **Edition distinction matters:** the answer is the first NES game; the
  sequel (The Great Waldo Search) is a different game. Scope states this;
  "first of its name? Yes" (Q16) turns on it.
- Tail begins mid-round (11 already asked); pre-tail questions are not
  individually recoverable and the ledger starts at checkpoint 11.

## Ep 872 — Death's Door (gs20q-872)

- **Late-round off-by-one:** checkpoints 5/10/15 match exactly, but "one
  question and a guess" (4101.78s) implies 19 used where 18 are cleanly
  identifiable. The unanswered "do you fly?" probe (4060.22–4064.18s, no
  clean host answer in the transcript — the team talks it through
  themselves) is the likely 19th charged turn; ledger slot 19 is marked
  as such rather than filled with a reconstructed question.
- **"Multiple entries in series? No" (Q11) vs sourced fact:** Wikipedia
  calls Death's Door a sequel to Titan Souls. The host's No is defensible
  under the question's apparent intent (multiple Death's Door entries) but
  the tension is flagged in the trait note for QA to rule on.
- Solver credited in-discussion by first name only; surname not stated in
  this episode and not recorded.
- The 2D/3D questions were deliberately never asked (3825.24s) — excluded,
  listed under `not_counted`.

## Ep 873 — Splatterhouse 2 (gs20q-873)

- **Late-round off-by-one (same pattern as 872):** checkpoints 5/10/15
  match exactly; after the brawler answer, "One question and one guess"
  (4278.89s) implies 19 used where 18 are cleanly identifiable. One
  question is not recoverable (candidates: the joke underpants follow-up
  at 4030.77s, or a merged ask). The mask question is ledgered as "19/20".
- **Equivocal answer:** "Play an undead character?" — host: "I don't think
  so" (4178.00s). Recorded as `unknown` in the history traits (hero is
  mask-possessed, not undead); not rounded to No.
- **"Targeted at adults? Yes"** was answered via the game's later Virtual
  Console M-rating (explained post-round, 4425.15s) — an anachronistic
  basis for a 1992 release; noted in the trait.
- **"Ever an arcade game? No"** is true of Splatterhouse 2 but the original
  Splatterhouse was an arcade game — predicate distinction flagged.
- Title as transcribed ("Splatterhouse two"); accepted titles include the
  Japanese name *Splatterhouse Part 2*.
- Repeated "8-bit game?" probe (4060.60s) was called out in-show as a
  repeat and not double-counted.

## Ep 874 — Skies of Arcadia Legends (gs20q-874)

- **Joke question excluded by checkpoint arithmetic:** the opening "What
  was his pick?" (3191.06s) was jokingly declared to count on air ("19
  questions left", 3202.30s), but the Q5 checkpoint matches the enumeration
  without it. Recorded count 11 (12 if the joke is taken literally) — the
  card follows the checkpoint, with the joke under `not_counted`.
- SUPERSEDED 2026-10-14 (Dot QA rounds 1–2; see the cleanup sections
  below): the answer is now recorded as Unknown in both the ledger (round 1)
  and the round-history trait (round 2); the sourced playable position is a
  separate playable trait. Original flag text: **Equivocal answer:** "Do
  you pirate a sky ship in it?" — "I think so" (3382.45s). Recorded as true
  with the equivocation noted.
- **Edition precision:** the answer is the GameCube *Legends* port, not the
  2000 Dreamcast original; scope, facts, and accepted titles are scoped to
  Legends. The cancelled PS2 port corroborates Q6's No.
- **Release-day discrepancy in sources:** NA Legends release given as
  28 January 2003 (Wikipedia text) vs 27 January 2003 (some databases).
  Card records January 2003 only.
- The RPG question was asked twice in overlapping speech and counted once.
- Solver credited post-credits by first name only; surname not stated in
  this episode and not recorded.

## Dot QA cleanup applied 2026-10-14

Applied per Dot's QA post (2026-10-14 14:16 EDT) on the ten cards in
`cards-remaining-v0.4.json` and eps 862/863 in `cards-v0.4.1.json`. No round
counts, ledgers, or solved outcomes were changed; both files re-validated as
parseable JSON after editing.

### Playable facts

- **864 Apex Legends** (`cards-remaining-v0.4.json`, `game.playable_scope`):
  Android/iOS removed from the same-game platform list. The 2022 Android/iOS
  release (Apex Legends Mobile) is now recorded as a separate mobile build,
  not a port of the main game, and outside the playable scope.
- **864 Apex Legends** (`game.round_history_traits` → "On a Nintendo
  platform"): provenance note corrected — the game first reached a Nintendo
  platform via the Nintendo Switch release (9 March 2021); a Nintendo
  Switch 2 version (2025) is now noted alongside it.
- **866 24: The Game** (`game.playable_traits`): the combined
  "Espionage / counterterrorism-themed" trait was split. "Counterterrorism-
  themed" is now its own trait set to **true** (sourced). A new trait
  "Military/espionage (broader predicate, as asked on air)" is set to
  **Unknown**, with a note that the host's on-air "No" (kept in
  `round_history_traits` with its dispute note) must never be served as a
  settled playable answer. A cross-note was also appended to the history
  trait pointing to this playable-side ruling.
- **869 Fall Guys** (`game.facts` → Publisher): Epic/Mediatonic handoff
  year corrected to **2021** (Epic acquired Mediatonic's parent Tonic Games
  Group in 2021). 2022 now appears only as the free-to-play relaunch.
  (Round-2 note: this bullet originally ended "…at which Epic became
  publisher" and the Publisher fact itself still carried the 2022 claim;
  both are corrected — publishing rights transferred in 2021. See "Dot QA
  round-2 cleanup applied 2026-10-14".)
- **869 Fall Guys** (`game.round_history_traits` → "Cartridge-based"): the
  Switch game-card explanation for the host's "Yes" was removed. The answer
  stays in round history; the note now records that the original 2020
  PS4/Windows release was disc/download and that the underlying predicate
  is **Unknown** per sources.
- **870 Overlord** (`game.playable_traits` → "Multiplayer mode (original
  2007 release)"): trait renamed and given an explicit status —
  "historical only — describes the original release; not a current playable
  trait" — with a note that the 2007 release's multiplayer is historical
  and must not be served as a current playable answer.

### Schema / history

- **862 Toy Story 3** (`cards-v0.4.1.json`, `round.yes_no_questions` and
  `round.title_guesses`): the prose strings ("null for the full round…")
  replaced with actual JSON **null** values. The explanation remains in
  `round.split_confidence`; the tail-observed split stays in
  `round.tail_observed_split`. A scan of both files confirms no other data
  field carries a string "null" (remaining mentions are inside
  confidence/notes prose, as intended).
- SUPERSEDED 2026-10-14 (Dot QA round-2 cleanup; see "Dot QA round-2
  cleanup applied 2026-10-14" below): the compressed-slot presentation
  described in this bullet was replaced by individually observed entries
  with unsupported indices null. Original round-1 text: **871 Where's
  Waldo?** (`round.ledger_from_checkpoint_11`): timestamp fields separated
  cleanly for the compressed slots 12–14. Each entry now carries `n_basis`
  (slots 12–14 = inferred from the 11- and 15-question checkpoints) and `t`
  / `t_basis` (slot 12's t = 4305.20 is the observed timestamp of the
  host's asterisked answer, now moved out of the answer prose; slots 13–14
  have t = null, not observed). Slot 15 is marked observed via the host's
  "that's 15" checkpoint. A new `round.ledger_field_semantics` field
  states the n/t semantics explicitly.
- **874 Skies of Arcadia Legends** (`round.ledger` Q10, "Do you pirate a
  sky ship in it?"): the answer value changed from the prose
  `Yes ('I think so')` to **Unknown**; the equivocation is preserved in a
  new `answer_note` field with its transcript timestamp (3382.45s).
- **872 Death's Door**: cross-references added in all three places — the
  sourced "Series relation" fact in `game.facts` now notes the round's
  Q11 "Multiple entries in series? No" and why it is defensible; the
  "Multiple entries in series" entry in `game.round_history_traits`
  points back to the Series relation fact; ledger Q11 carries a short
  cross-reference note.
- **865 Palworld** (`game.facts` → "Early-access release"): citation
  locator corrected. It previously read "lead", but the lead gives only
  the month/year (January 2024); the exact day (19 January 2024) is in
  the article's Release section. Locator now reads "Release section
  (exact day: 19 January 2024) + lead (early-access platforms and
  month)". (Verified against the live Wikipedia page 2026-10-14; all
  other 865 locators were checked against the same page and matched.)

## Dot QA round-2 cleanup applied 2026-10-14

Applied per Dot's second-round QA on `cards-remaining-v0.4.json`. No
charged totals or solved outcomes changed. The only ledger whose entry
representation changed is 871 (per Dot's instruction); all other ledger
entry counts are unchanged. All ten cards' `verification.qa` now records
round 2 and the return for the freeze pass.

- **869 Fall Guys** (`game.facts` → Publisher): the round-1 fix had
  corrected the acquisition date but the fact still said Epic "became
  publisher from the 2022 free-to-play relaunch". Now reads: Epic acquired
  Mediatonic's parent Tonic Games Group in 2021 and publishing rights
  transferred to Epic in 2021; 2022 is only the free-to-play relaunch. A
  scan of the whole 869 card confirms no remaining field ties Epic
  publishing to 2022 (the on-air submitter note in `outcome` is a quote of
  what was read on air and is unchanged).
- **Split fields set to real JSON null** (`round.yes_no_questions`):
  eps 866, 869, 870, 872, 873 previously carried prose strings; each is now
  `null` with its explanation moved into `round.count_convention`.
  `title_guesses` on those cards was already an integer and is unchanged.
  Additionally, because their round openings are missing, the full-round
  splits for **870** (`title_guesses` also set to null) and **871**
  (`yes_no_questions` 16 → null, `title_guesses` 1 → null, explanation in
  `round.evidence_completeness`) now carry explicit uncertainty — an early
  title guess cannot be ruled out for either.
- **871 Where's Waldo?** (`round.ledger_from_checkpoint_11`): restructured
  from 6 compressed entries to 8 individually observed entries, grounded in
  the raw transcript segments. Directly observed: "Based on a book?" asked
  4295.16s (asterisked answer to 4312.68s) — it precedes the host's
  "you've asked 11" callout at 4353.96s, which is why the old ledger's
  placement of its 4305.20s timestamp after that checkpoint was impossible;
  "License features an iconic character?" 4356.84s; "Spooky game?" 4382.68s;
  "Based on books for kids?" 4455.60s; the "pixel hunt" probe 4476.76s
  (equivocal response, no clean yes/no); "Does the character wear a hat
  and glasses?" 4501.52s with the host's "that's 15" in the same segment;
  "Is it the first of its name?" and the closing title guess, both within
  4523.44–4529.20s. Indices: n = 15 (observed callout) and n = 16–17
  (derived from that checkpoint plus the recorded 17-turn total); all other
  entries have n = null with `n_basis` stating why. The claim that the
  pixel-hunt probe "was evidently not counted" is removed from the card
  (`round.not_counted` is now empty) and from this doc (superseded above);
  the probe's counted status is unresolved. `round.ledger_field_semantics`
  rewritten to match. Charged total (17) and checkpoints unchanged.
- **874 Skies of Arcadia Legends** (`game.round_history_traits` →
  "Pirate a sky ship in it"): value changed from `true` to **Unknown**,
  matching the ledger Q10 value, with the equivocation note kept. The
  independently sourced playable position remains the separate playable
  trait "Sky-pirate protagonist with airship travel" (`playable_traits`,
  sourced from Wikipedia) — distinct from what the host answered.
- **872 Death's Door**: the cross-pointer "(see not_counted)" in
  `round.yes_no_questions` pointed at the wrong field — `not_counted`
  records the never-asked 2D/3D questions. The implied-20th-question
  explanation actually lives in `round.count_convention` and at ledger
  entry 19 (the likely "do you fly?" probe slot, 4060.22s); with
  `yes_no_questions` now null and its explanation moved into
  `count_convention`, the pointer is corrected by that relocation. The
  round-1 series cross-references are a different set of fields and are
  untouched.
- **866 24: The Game** (`game.playable_traits` → "Counterterrorism-
  themed"): source locator changed from "lead (based on the 24 series;
  story set between its second and third seasons)" to **"Plot"** — the
  sourced position is grounded in the Wikipedia article's Plot section.
  `source_url` verified as the 24: The Game Wikipedia page.
