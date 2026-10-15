# Value Proposition

Each value proposition closes at least one gap from [the gap analysis](gap-analysis.md), names what it costs, and says how a competitor would respond.
The assumptions these propositions rest on are in [the assumptions log](../assumptions.md), and the decisions that changed them are in [the decisions log](../decisions.md).

The 2 October kickoff changed which proposition leads. The customer asked for a voice in the ear during the run. [GAP-01](gap-analysis.md#gap-01) was not confirmed, so a plan that explains its own changes is not a proposition in this file. Phone-only and beginner-to-intermediate did survive, and that is the user in [GAP-02](gap-analysis.md#gap-02).

## VP-01

A voice coach during the run

- **Status:** Active
- **User:** a beginner to intermediate runner, often without a sports watch, who will not keep looking at the phone.
- **Problem:** the products he can already use show pace, distance, and heart rate on a screen. He has to take the phone out to know them, and nothing talks him through the run.
- **What we do that the alternatives do not:** during the run the phone speaks a simple intensity cue (hard, then easier, then jog) and the stats it already has: time, pace, and distance. He can ask aloud for one of those three and hear the answer. Heart rate is spoken only when a connected device provides it, which the Week 3 slice does not do. The first release is English, on Android, and the answer is chosen on the phone.
- **Measured by:** on a phone with no watch, the runner hears time, pace, and distance at least once within three minutes without opening the screen, hears hard, easier, or jog when the effort changes, and hears the elapsed time when he asks how long the run has been going.
- **Closes:** [GAP-02](gap-analysis.md#gap-02).
- **Rests on:** [ASM-01](../assumptions.md#asm-01), [ASM-02](../assumptions.md#asm-02), [ASM-03](../assumptions.md#asm-03), [ASM-04](../assumptions.md#asm-04), [ASM-06](../assumptions.md#asm-06), [ASM-07](../assumptions.md#asm-07), [ASM-09](../assumptions.md#asm-09).
- **What it costs:** without a watch we cannot promise heart rate, so the coach speaks time, pace, and distance, and adds heart rate only when a wearable is connected. Keeping the processing on the phone limits how capable the spoken coach can be. We give up an adaptive training plan in the first release so this can ship.
- **How a competitor would respond:** Runna (ALT-01) and Garmin Coach (ALT-02) already own plan adaptation and could add spoken stats in a release. The customer uses Google Health and dislikes it because it makes him stare at the stats and does not talk. Spoken stats are not a deep moat. They are the part he said his current app does not do.
- **Changed:**
  - Rewritten from a plan that explains its own changes into the in-run voice coach, which the `Customer` described as the base, instead of the direction this file stated before the kickoff. This is not a decision, and [the kickoff report](../../reports/week-01/meeting-report.md#action-points) carries the question forward as action point A2.
  - Restated for the query-response scope in [DEC-008](../decisions.md#dec-008): the coach also answers a spoken question about time, pace, or distance. [ASM-08](../assumptions.md#asm-08) is `Refuted`, so this proposition no longer rests on it. The Week 3 binary uses the phrase matcher in [DEC-009](../decisions.md#dec-009). The story criteria for that scope are already [US-04](https://github.com/Running-Coach-App/running-coach-app/issues/40).

## VP-02

Two preset sessions, after the voice coach

- **Status:** Active
- **User:** the same runner, once VP-01 works.
- **Problem:** he does not want to design each interval himself, and he has not seen a goal-setting screen he trusts. He asked for a small number of programmes the app proposes, after the talking coach is in place.
- **What we do that the alternatives do not:** offer two preset sessions the coach speaks, for example a steady run and a hard/easy interval, and he picks one. This release does not build a weekly plan that rewrites itself.
- **Measured by:** the runner can start either preset and hear that session's cues without looking at the phone.
- **Closes:** [GAP-02](gap-analysis.md#gap-02), as a fixed spoken session rather than a post-run rewrite. [GAP-01](gap-analysis.md#gap-01) and [GAP-03](gap-analysis.md#gap-03) are `Dropped` in [DEC-007](../decisions.md#dec-007).
- **Rests on:** [ASM-01](../assumptions.md#asm-01), [ASM-02](../assumptions.md#asm-02), [ASM-07](../assumptions.md#asm-07).
- **What it costs:** two presets cannot serve a runner who wants a race plan. We give up granular goal setting, meal advice, and automatic plan edits.
- **How a competitor would respond:** Runna (ALT-01) and Hal Higdon (ALT-03) already ship full plans. They do not need to answer two spoken presets. Copying their plans is not this proposition.
- **Changed:**
  - Narrowed from adaptive coaching with only a phone to two preset sessions, and placed after the in-run coach rather than alongside it, because the `Customer` asked for presets on top of the coach. Action point A2 in [the kickoff report](../../reports/week-01/meeting-report.md#action-points) puts the order to him.
  - Restated so the two presets sit on the coach from [DEC-008](../decisions.md#dec-008), which also answers spoken stat questions. Whether the presets still follow that coach is still open, and [the Week 3 script](../../reports/week-03/meeting-script.md) asks it. [US-06](https://github.com/Running-Coach-App/running-coach-app/issues/42) is not in the Week 3 candidate.
