# Fire Superiority as Temporary Mobility

## Small-unit fire and maneuver as a causal system

**Repository:** Tactics Brainstorm  
**Status:** Research working paper  
**Date:** 2026-09-19

## Abstract

Small-unit infantry tactics are often represented as a damage contest: one element fires while another moves because firing reduces the enemy faster. Historical and modern doctrine describe a more interesting causal relationship.

In U.S. Army doctrine from 1944, a rifle squad first sought **fire superiority** before advancing. FM 7-10 defined that state functionally: enemy fire had to become inaccurate or reduced enough to be ineffective, and the effect had to be maintained while part of the squad moved. Modern U.S. Army support-by-fire training preserves the same logic in different language: support-by-fire fixes, suppresses, or destroys threats **to increase the supported force's freedom of movement**. Marine infantry instruction is even more direct: suppression is what makes rushes effective.

The recurring relationship is therefore not:

```text
FIRE -> DAMAGE
```

but:

```text
FIRE -> REDUCED ENEMY INTERFERENCE -> TEMPORARY MOVEMENT FREEDOM
```

This paper treats that relationship as a candidate small-unit tactical law.

---

# 1. The 1944 rule: gain fire superiority before movement

War Department FM 7-10, *Rifle Company, Infantry Regiment*, dated 18 March 1944, describes rifle-squad fire and maneuver in explicitly causal terms.

At the first firing position, the squad seeks to gain fire superiority over the enemy. The manual defines fire superiority by its **effect on hostile fire**: friendly fire must be accurate and intense enough that hostile fire becomes sufficiently inaccurate or reduced in volume to be ineffective. Once gained, that state must be maintained.

The manual then describes the division of labor:

- enough soldiers remain in position to maintain fire superiority;
- the automatic rifle is particularly valuable because it can sustain a large volume of fire;
- other soldiers move forward to new firing positions;
- from those positions they fire to cover the movement of the men behind them;
- this alternation continues until the squad is close enough to assault.

Terrain changes the requirement. FM 7-10 notes that movement across open ground against an unbeaten enemy requires especially strong fire superiority, while cover, defilade, depressions, rises, and short rushes reduce exposure.

The important mechanism is:

> **Movement becomes feasible when enemy observation and effective fire are sufficiently degraded for long enough to cross the exposed interval.**

This is a state change, not a hit-point exchange.

---

# 2. Modern continuity: support by fire exists to create freedom of movement

The U.S. Army Maneuver Center of Excellence's 2025 training outline for **Conduct Support by Fire - Platoon** states the standard directly: the platoon establishes support-by-fire positions to fix, suppress, or destroy the threat **in order to increase the supported force's freedom of movement**.

The task also makes clear that suppression is dynamic rather than binary. The support element must:

- mass fires against relevant threats;
- prevent the threat from placing accurate fires on the maneuver force;
- maintain awareness of the maneuver force's route and progress;
- shift, refocus, distribute, or cease fires as the tactical geometry changes;
- move to alternate firing positions when necessary to maintain effective fires.

The implication is important:

> **Suppression has geometry, timing, and a supported recipient.**

A unit is not simply "suppressed" everywhere and forever. A particular source of hostile interference is being reduced from a particular direction for a particular friendly movement, and that relationship can expire when the supporting fires are masked, shifted, stopped, or become ineffective.

---

# 3. Fire and movement versus fire and maneuver

Marine Corps infantry instruction distinguishes two closely related ideas.

**Fire and maneuver** assigns different missions to different elements: a maneuver element moves while a separate support-by-fire element supports it.

**Fire and movement** occurs when elements or individuals alternate their own firing and moving by bounds.

The distinction matters because it suggests two nested scales of the same law.

At the lowest scale:

```text
FIRE TEAM A FIRES -> FIRE TEAM B MOVES
FIRE TEAM B FIRES -> FIRE TEAM A MOVES
```

At a larger scale:

```text
SUPPORT ELEMENT FIRES -> MANEUVER ELEMENT MOVES
```

The mechanism is unchanged. One element temporarily spends its capacity to act offensively in order to reduce the enemy's capacity to interfere with another element's movement.

This can be interpreted as a **transfer of freedom of action**.

---

# 4. Suppression is not destruction

The doctrine repeatedly separates suppression from destruction.

That distinction is useful because a force does not always need to eliminate a threat before moving. It needs the threat's ability to interfere reduced below the level that prevents the intended action.

This suggests a threshold model:

```text
enemy_interference > movement_tolerance
    -> exposed movement is blocked or very costly

enemy_interference <= movement_tolerance
    -> movement becomes feasible
```

The threshold depends on:

- exposure time;
- available cover and concealment;
- distance of the bound;
- enemy weapon effectiveness;
- direction and field of fire;
- friendly suppression;
- obscuration;
- surprise;
- urgency and acceptable risk.

The decisive variable is therefore not simply "how much firepower do I have?" It is:

> **Can I reduce the relevant hostile interference below the tolerance required for this particular movement, for the duration of this particular movement?**

---

# 5. Fire superiority is local and directional

A useful model should resist treating suppression as a global debuff.

A machine gun covering an open lane may prevent movement through that lane while having little effect on a route hidden behind a hedgerow.

Likewise, a friendly support element may suppress the weapon from one angle while a maneuver element moves through another.

Therefore the relevant relationship is closer to:

```text
SUPPRESSION(source, target, direction, interval)
```

than:

```text
enemy.suppressed = true
```

This immediately makes terrain important without requiring a huge simulation.

Cover, concealment, dead ground, defilade, walls, hedgerows, buildings, and smoke matter because they change which enemy systems can interfere with which movements.

---

# 6. Suppression creates a temporary tactical window

Because the supporting element must eventually shift, cease, reload, reposition, conserve ammunition, or avoid masking and fratricide, suppression naturally has duration.

This creates a small-unit timing problem:

```text
GAIN FIRE SUPERIORITY
        ↓
OPEN MOVEMENT WINDOW
        ↓
MANEUVER BEFORE WINDOW CLOSES
        ↓
REESTABLISH FIRE FROM NEW POSITION
```

The moving element is therefore not merely consuming movement points. It is exploiting a temporary state created by another element.

This creates a causal rhythm that can scale upward:

```text
SUPPRESS -> MOVE -> REPOSITION -> SUPPRESS AGAIN
```

The battlefield advances because units repeatedly create and consume temporary permissions.

---

# 7. Breaching exposes the same law more clearly

Modern Army breaching doctrine divides forces into support, breach, and assault functions.

The support force suppresses or neutralizes enemy systems able to interfere with the reduction area. The breach force changes the obstacle. The assault force exploits the resulting lane or foothold.

That sequence can be written:

```text
SUPPORT REDUCES ENEMY INTERFERENCE
        ↓
BREACH FORCE GAINS WORKING TIME
        ↓
OBSTACLE STATE CHANGES
        ↓
ASSAULT FORCE GAINS A NEW ROUTE
```

This is a particularly clean combined-arms example because two different forms of freedom are being created:

1. **fire superiority creates temporary freedom to act;**
2. **engineering creates persistent freedom to move.**

The first protects the transformation. The second outlives it.

That relationship connects directly to the existing Tactics Brainstorm combat-engineering work.

---

# 8. Candidate tactical law: Suppression-Mobility Coupling

A compact statement:

> **Friendly movement through enemy-covered space becomes feasible when friendly action reduces the enemy's effective interference below the movement's exposure tolerance for long enough to complete the bound.**

Or, in a deliberately rough model:

```text
M_feasible = (I_enemy × E_movement) <= (C_terrain + S_friendly + O_obscuration + R_tolerance)
```

Where:

- `I_enemy` = effective hostile interference against the route;
- `E_movement` = exposure created by the intended movement;
- `C_terrain` = protection supplied by terrain;
- `S_friendly` = reduction of hostile effectiveness produced by friendly suppression;
- `O_obscuration` = reduction of hostile observation/fire produced by smoke or similar effects;
- `R_tolerance` = risk the moving element can accept.

This is not proposed as a literal combat equation. It is a causal sketch showing which relationships should exist.

---

# 9. Why this matters for a minimal small-unit model

A very small simulation can express the law with only a few semantic states.

Example friendly elements:

- Infantry 1
- Infantry 2
- Infantry 3
- Engineer 1

Example enemy state:

- defended obstacle;
- one known enemy fire source covering the approach.

The game does not need ballistic simulation.

It needs to distinguish:

```text
UNSUPPRESSED
SUPPRESSED
MOVEMENT WINDOW OPEN
MOVEMENT WINDOW CLOSING
BREACH IN PROGRESS
BREACH OPEN
```

Then sequence creates meaning.

```text
INF 1 SUPPRESS
ENG 1 BREACH
INF 2 MOVE
```

can succeed because Infantry 1 temporarily reduces interference, allowing Engineer 1 to work, and the engineer's persistent terrain change allows Infantry 2 to move.

But:

```text
ENG 1 BREACH
INF 2 MOVE
INF 1 SUPPRESS
```

may fail or become costly because the support effect arrives after the exposed actions that needed it.

The tactical meaning comes from **causal order**, not arbitrary combo bonuses.

---

# 10. Research propositions

## Proposition 1: Fire should primarily modify enemy interference, not merely enemy health

Damage may exist, but the most important immediate effect of small-unit fire can be the change in what other friendly elements are able to do.

## Proposition 2: Movement should have exposure

Moving through dead ground, along a covered route, or across an open lane should not be equivalent.

## Proposition 3: Suppression should be local, directional, and temporary

A global suppression meter destroys the geometry that gives fire and maneuver its tactical meaning.

## Proposition 4: A firing element spends opportunity to create opportunity elsewhere

The supporting element cannot simultaneously be everywhere or do everything. This creates the elementary form of command composition.

## Proposition 5: Sequence should emerge from conditions

`SUPPRESS -> BREACH -> MOVE` should work because each action creates a condition needed by the next, not because the game recognizes a memorized combo.

## Proposition 6: Persistent actions and temporary actions should interact

Suppression is temporary. A breach can persist. The tactical art lies partly in using temporary effects to create durable changes.

---

# 11. Working law for Tactics Brainstorm

> **FIRE BUYS TIME IN EXPOSED SPACE. MANEUVER SPENDS IT.**

Expanded:

> **Suppression is a temporary transfer of freedom of action: one element reduces the enemy's ability to interfere so another element can move, work, or assault. Terrain determines how much suppression is required; timing determines whether the opportunity is successfully consumed.**

This may be the smallest useful infantry law for a reality-derived command simulation.

---

# Sources

1. U.S. War Department, **FM 7-10, Rifle Company, Infantry Regiment**, 18 March 1944, especially the rifle-squad fire-and-maneuver discussion around paragraphs 153-155.  
   https://www.ibiblio.org/hyperwar/NHC/NewPDFs/USArmy/US%20Army%20Field%20Manuals/USArmy,%20Infantry%20FM%20Rifle%20Company,%20Infantry%20Regiment%20FM%207-10%201944-03-18.pdf

2. U.S. Army Maneuver Center of Excellence, **Training and Evaluation Outline 07-PLT-3000: Conduct Support by Fire - Platoon**, approved/effective 17 March 2025.  
   https://rdl.train.army.mil/catalog-ws/view/100.ATSC/A8BA5A93-61B5-46BD-B970-47DF7ED18C72-1491839008928/report.pdf

3. U.S. Army, **ATP 3-21.8, Infantry Platoon and Squad**, April 2016 with Change 1, 23 August 2016, especially discussions of fire superiority, support by fire, maneuver, and breaching.  
   https://upload.wikimedia.org/wikipedia/commons/7/7a/ATP_3-21.8_Infantry_Platoon_and_Squad_April_2016_%28Change_1%29.pdf

4. U.S. Marine Corps, The Basic School, **Rifle Squad Tactics**, especially the distinction between fire and maneuver and fire and movement, and the role of suppression in enabling rushes.  
   https://www.trngcmd.marines.mil/Portals/207/Docs/TBS/W2B0011XQ%20Rifle%20Squad%20Tactics.pdf
