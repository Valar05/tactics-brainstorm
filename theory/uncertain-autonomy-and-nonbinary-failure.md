# Uncertain Autonomy and Nonbinary Failure

**Date:** 2026-09-14
**Status:** active tactics brainstorm

## Trigger

Arcane Manifold's homing system was not simple. Drew describes it as the hardest part of the game, revised many times. The projectile begins under direct player guidance while close to the player, then transfers to autonomous target selection after a distance threshold. The autonomy contains substantial foreknowledge encoded through repeated iteration, yet it still sometimes chooses the wrong target. It can also collide with walls.

The important asymmetry is this:

```text
WRONG TARGET != USELESS
WALL != TARGET
```

Every valid enemy target can still be hurt, so an autonomous choice can be tactically wrong while remaining locally useful. A wall collision is different: it can be a true null sink.

## Generalization

Autonomy should not be evaluated as binary correct / incorrect. The more useful quantity is the payoff distribution of plausible local choices.

```text
perfect choice -> best available contribution
wrong but valid choice -> degraded contribution
null sink -> no useful contribution
catastrophic choice -> harms the larger system
```

A robust distributed system raises the probability that local errors fall into the second category rather than the third or fourth.

## Safe action envelope

The central design question becomes:

> How much of the local decision space remains useful even when the autonomous element chooses imperfectly?

Call this the **safe action envelope**.

If many locally plausible actions still advance the larger objective, autonomy can be imperfect without becoming brittle. This reduces the amount of central supervision required.

Arcane Manifold achieves this accidentally and then deliberately through target ontology: every legitimate target is damageable. The homing algorithm can therefore mis-prioritize without necessarily wasting the projectile.

Walls expose the boundary of the envelope. They are useful precisely because they prove that graceful degradation is not universal. The system still has null sinks.

## Combined-arms implication

The lesson for abstract combined-arms theory is not merely `delegate authority`.

It is:

> **Delegate authority into a decision space engineered so that many imperfect choices remain productive.**

This reframes mission-level robustness. A commander or autonomous subsystem does not need clairvoyance if doctrine, objectives, geometry, and allowable actions are shaped so that mistakes are usually suboptimal rather than useless.

### Revised authority lifecycle

```text
INTENT
-> ENCODE PRIORITIES / CONSTRAINTS
-> RELEASE
-> LOCAL JUDGMENT
-> USEFUL OR DEGRADED ACTION
-> RECALL / CORRECTION WHEN WORTH THE COST
-> RECOMPOSE
```

The foreknowledge belongs before release. Local judgment is then bounded by that encoded knowledge, but remains fallible.

## New metric: useful-error ratio

A useful conceptual metric:

```text
USEFUL-ERROR RATIO = P(action still contributes | local choice was not optimal)
```

High useful-error ratio means the system tolerates imperfect autonomy.
Low useful-error ratio means every local mistake demands expensive central correction.

A strong distributed system should seek both:

- good local judgment;
- a world / doctrine / task structure where imperfect judgment is still often useful.

## Null sinks

Walls matter.

Any theory of resilient autonomy that discusses only wrong-but-useful choices is incomplete. Systems also contain states where effort disappears entirely.

Therefore map:

- productive targets;
- degraded-but-useful targets;
- null sinks;
- harmful sinks.

Robustness improves either by making local judgment better or by shrinking the sink regions.

## Compact law

> **Do not demand perfect local decisions. Build the system so that most imperfect decisions still have somewhere useful to land.**

And the corollary:

> **A wall is load-bearing because it reveals where graceful degradation stops.**
