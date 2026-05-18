# THE PROMETHEUS DRIFT — PROJECT HANDOFF DOCUMENT
## Paste this into any new Claude conversation to resume work instantly.
## Last updated: Sector 2 complete. Sector 3 ready to write.

---

## WHAT THIS IS

A choose-your-own-adventure science campaign app for a 6th grade classroom. Built as a single HTML file, hosted on GitHub Pages. Teacher projects it at the front of the room. Three classes tracked simultaneously with separate save states using localStorage. No student devices needed.

**Live file:** `PrometheusDrift.html` in a GitHub repository called `science-campaigns`.

---

## THE STORY

**Campaign name:** The Prometheus Drift
**Ship:** The *Prometheus* — a research vessel that went silent 6 months ago
**Player ship:** The *Argo* — the rescue vessel the class is crew of
**AI guide:** GAIA — the Prometheus's onboard AI who has been alone for 6 months

**GAIA's voice:** Warm and relieved by default. Dry humor under pressure. Never panics. Treats the class as genuine scientists.

**GAIA voice examples:**
✓ "I have been hoping someone would come. I have a great deal of data and nowhere useful to send it."
✓ "Interesting decision. I'm sure that'll work out fine. Updating damage report now."
✓ "Results pending. I'd recommend finding out what happened before creating new things to regret."
✓ "The crew voted. Something happened. You haven't looked yet. Perhaps do that first."
✓ "No pun intended. Actually, pun very much intended."
✗ Never panic, condescend, or explain things kids should figure out
✗ Never use exclamation points in GAIA's voice

**Sector 1 cliffhanger:** "The pattern of changes all points to a single source. Somewhere deeper in the ship. In the section the crew hasn't reached yet. Where the temperature is still dropping. Where the atoms themselves seem to be behaving according to rules that shouldn't exist. Get some rest, crew. Things are about to get stranger."

**Sector 2 cliffhanger:** "The research lab contained something else. In the back, sealed in a secondary containment unit — the original crew's final research notes. I have begun reading them. I am not going to tell you what they say yet. But the temperature anomaly was not the only experiment running on this ship. The next system — connected to how this ship stores and transfers energy — may be more significant than anything we have found so far. Get some rest. Sector 3 begins with the ship's energy systems."

---

## CRITICAL TERMINOLOGY

**Use "Sector" NOT "Act"** throughout all content, UI text, and GAIA dialogue.
- Sector 1, Sector 2, Sector 3, Sector 4, Sector 5
- JavaScript variable names (cls.act, d.act) stay as-is — internal only

---

## THE STAT SYSTEM

Four stats. Updated ONLY during the REVEAL screen (next class day). Never immediately after a choice.

| Stat | Icon | Color | Tracks |
|---|---|---|---|
| Power Reserves | ⚡ | #00c8ff | Energy available |
| Hull Integrity | 🛡 | #00ff88 | Structural health |
| Data Collected | 📡 | #aa66ff | Scientific findings |
| Crew Morale | 👥 | #ffaa00 | Team wellbeing |

**Warning:** stat below 30% — GAIA flags, options may restrict.
**Crisis:** stat hits 0%, or two stats below 20% — triggers failure.
**Failure tiers:** (1) forensics + reset, (2) choices restricted, (3) GAIA narrows to 2 options.

**Section colors (consistent across ALL graphs):**
- Section A: #00ff88 · Section B: #00c8ff · Section C: #ff3355
- Section D: #aa66ff · Section E: #7be3ff · Section F: #ff8800

---

## DAILY CLASSROOM FLOW

Always the same structure — critical for neurodiverse students.

**Choice Days (⚡):** Scenario → Exit Ticket (timer) → Discussion (timer) → Final Vote
**Lesson Days (📖):** Scenario → Reading Timer
**Graph Days (📊):** Scenario → Work Timer
**Climax Days (🏁):** Scenario only

After vote: Commit → Processing screen (GAIA cliffhanger, stats hidden) → Save → Home.
Next class: Launch → auto-routes to REVEAL screen → stats update live → mission.

**Cliffhanger protection:** Next Day button BLOCKED when pendingDeltas exist. GAIA cycles:
- "Results pending. I'd recommend finding out what happened before creating new things to regret."
- "The crew voted. Something happened. You haven't looked yet. Perhaps do that first."

---

## APP FEATURES (DO NOT CHANGE ENGINE)

- **localStorage** — survives browser close, works on same machine
- **Three-class tracking** — separate stat/branch/day state per class
- **Pending deltas** — stats frozen until reveal screen
- **Processing screen** — GAIA cliffhanger after commit, no stat reveal
- **Reveal screen** — dramatic live stat update, consequence text
- **Forensics screen** — CER framework, decision timeline, failure tiers
- **Day navigator** — dropdown shows ALL sectors and days, jump anywhere instantly
- **Presentation mode** — full-width center + horizontal stats bar visible to class
- **Day-type banner** — color coded, shows day type + day number of total
- **Teacher notes panel** — right panel only, hidden in presentation mode
- **Show Answer Graph** — on dataset comparison days, reveals all answers after discussion
- **GAIA block messages** — cycling dry humor, blocks Next Day when reveal pending

---

## TEACHER NOTES

**Never appear in center panel or presentation mode.** Only in right teacher panel. Includes: graph notes, display instructions, dataset answers, short day recommendations, bridge to next class.

---

## GRAPH PROGRESSION (DO NOT REGRESS)

| S1 Day 3 | Bar graphs — reading and comparing categories |
| S1 Day 7 | Bar vs. line — which tells the story better? |
| S2 Day 3 | Line graphs — reading trends, making predictions from slope |
| S2 Day 8 | Two lines, same graph — comparing Section C vs Section F |
| S2 Day 13 | Phase change curve — the flat line during state changes |
| S2 Day 18 | Which graph fits? — students choose type and defend reasoning |
| S3 | Pie charts — parts of a whole (energy distribution) |
| Campaign 2+ | Scatter plots, stem and leaf, box and whisker |

Students also do a "graph of the week" homework at ~5th grade level to build baseline literacy.

---

## CURRICULUM MAP

### CAMPAIGN 1: The Prometheus Drift (Physical Science)

| Sector | Topic | Standard | Weeks | Status |
|---|---|---|---|---|
| 1 | Atoms & Molecules | 6.P1U1.3 | 2 | ✅ COMPLETE |
| 2 | Kinetic Theory + States of Matter + Changes of State | 6.P1U1.1 + 6.P1U1.2 | 4 | ✅ COMPLETE |
| 3 | Energy (Kinetic & Potential) | 6.P4U2.5 | 2 | ⬜ NEXT |
| 4 | Resolution / Synthesis | All physical science | 1 | ⬜ |

### CAMPAIGN 2: The Lighthouse at the Edge of the Solar System (Earth & Space)
Stats: Navigation Accuracy, Solar Power, Signal Clarity, Earth Status. Status: ⬜ Not built.

### CAMPAIGN 3: The Vanishing (Life Science)
Stats: Biodiversity Index, Water Quality, Food Supply Stability, Community Trust. Status: ⬜ Not built.

---

## SECTOR 3 CONTENT NEEDED

**Topic:** Energy — Kinetic & Potential · **Standard:** 6.P4U2.5 · **~10 days**
**Savvas:** Energy Transfer module, Topic 1 Lesson 2

**Key concepts:**
- Objects store energy based on chemical composition, movement, temperature, gravitational field
- Kinetic energy = motion energy (proportional to mass, grows with square of speed)
- Potential energy = stored energy (gravitational, chemical, nuclear, elastic)
- Technology allows humans to store and use energy

**Vocabulary:** potential energy (GPE, chemical, nuclear, elastic), kinetic energy (radiant, sound, mechanical, thermal, electrical)

**Story hook:** Original crew's research notes (found end of Sector 2) reveal a second experiment connected to the ship's energy storage systems. GAIA believes the ship was trying to do something with energy storage that shouldn't be possible. The crew must understand kinetic and potential energy to figure out what.

**Graph focus:** Introduce pie charts — parts of a whole. Energy distribution across ship systems is a natural fit.

---

## ADDING NEW SECTOR CONTENT

Find in `PrometheusDrift.html`:
```
// SECTOR 3 CONTENT — DROP ZONE
```
Replace the entire `{ id:3, ... }` placeholder object with the new content object.

### Content object structure:
```javascript
{
  id: 3,
  label: 'Sector 3 · Energy',
  standard: '6.P4U2.5',
  days: [
    // CHOICE DAY:
    {
      day: 1, type: 'choice', isReveal: false,
      actLabel: 'Sector 3 · Energy',
      actTitle: 'Day title',
      gaia: 'GAIA narration — use <em>italics</em>',
      scenario: 'Story text. Use \\n for paragraph breaks.',
      exitTicketPrompt: 'Phase 2 text (choice days only)',
      discussionPrompt: 'Phase 3 text (choice days only)',
      choices: [
        {
          letter: 'A', text: 'Choice text', subtext: 'Sub text',
          deltas: { power: -5, hull: 0, data: 12, morale: 3 },
          branch: 'A-name',
          consequence: 'GAIA reveal text next class'
        }
      ]
    },
    // DEEPEN DAY:
    {
      day: 2, type: 'deepen', isReveal: true,
      actLabel: 'Sector 3 · Energy', actTitle: 'Day title',
      gaia: 'GAIA narration', scenario: 'Story text',
      readingFocus: 'Savvas Topic X, Lesson Y',
      gaiaReadingPrompt: '"GAIA directing crew to read."',
      vocabFocus: ['word1', 'word2'],
      noChoice: true, bridgeToNext: 'Teaser for next class'
    },
    // GRAPH DAY:
    {
      day: 3, type: 'graph', isReveal: false,
      actLabel: 'Sector 3 · Energy', actTitle: 'Day title',
      gaia: 'GAIA intro', scenario: 'Context',
      graphData: {
        title: 'Graph title',
        teacherNote: 'Teacher-only (right panel, never on screen)',
        // BAR: bars: [{ label: 'X', value: 85, status: 'safe' }], xLabel, yLabel
        // LINE: data: [{ label: 'Point 1', value: 42 }]
        // MULTI-LINE: multiLine: [{ section: 'Section C', values: [45,38,31], color: 'danger', note: 'teacher note' }], xLabels: ['0h','8h']
        // PHASE CURVE: phaseChangeCurve: [{ time: 0, temp: -40, phase: 'Solid' }]
        // DATASETS: datasets: [{ id: 'Dataset 1', description: '...', data: [{label:'A',value:85}], answer: 'teacher answer', hint: 'teacher hint' }]
      },
      gaiaGraphNote: '"GAIA on graph choice"',
      graphQuestions: ['1. Question', '2. Question'],
      shortDayNote: 'Short day: do questions 1-2 only.',
      noChoice: true
    },
    // CLIMAX DAY:
    {
      day: 10, type: 'climax', isReveal: true,
      actLabel: 'Sector 3 · Energy', actTitle: 'Sector Finale',
      gaia: 'GAIA synthesis', scenario: 'Resolution text',
      gaiaClosing: '"GAIA closing line bridging to Sector 4."',
      noChoice: true, isActEnd: true
    }
  ]
}
```

---

## ASSESSMENT APPROACH

**In-campaign:** CER exit ticket every choice day (Google Form, daily grade). Branch extinction forensics uses CER framework.

**External (Canvas):** Use GAIA's voice for questions.
- Instead of: "What is kinetic energy?"
- GAIA asks: "Mission Control needs you to explain why Section F's hull material began to soften. Use what you know about particle speed, thermal energy, and melting points to make your case."

End of sector: Savvas lesson review (low stakes). End of unit: Savvas test or CBAS (official grade). Graph days: questions serve as informal cross-curricular math assessment.

---

## FILES

| File | Purpose |
|---|---|
| `PrometheusDrift.html` | Campaign 1 — Physical Science (~248KB, active) |
| `HANDOFF.md` | This document — update at end of each work session |
| `Lighthouse.html` | Campaign 2 — Earth & Space (not yet built) |
| `Vanishing.html` | Campaign 3 — Life Science (not yet built) |

---

## TO START A NEW CONVERSATION

Paste this entire document, then add:

*"We are ready to write Sector 3 content — Energy, Standard 6.P4U2.5, approximately 10 days. Story hook: original crew's research notes reveal a second experiment connected to energy storage. Graph focus: introduce pie charts."*
