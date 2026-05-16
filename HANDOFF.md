# THE PROMETHEUS DRIFT — PROJECT HANDOFF DOCUMENT
## Paste this into any new Claude conversation to resume work instantly.
## Last updated: Act 1 complete, Act 2 ready to write.

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

**GAIA's voice:** Warm and relieved by default (she's glad the crew is finally there). Dry humor under pressure. Never panics. Treats the class as genuine scientists. Favorite words: "interesting," "efficient," "I will know if you skipped them." Example line: *"You solved the immediate problem. The hull, however, did not find it as satisfying."*

**Act 1 cliffhanger:** GAIA's closing line — *"The pattern of changes all points to a single source. Somewhere deeper in the ship. In the section the crew hasn't reached yet. Where the temperature is still dropping. Where the atoms themselves seem to be behaving according to rules that shouldn't exist. Get some rest, crew. Things are about to get stranger."*

---

## THE STAT SYSTEM

Four stats displayed on screen at all times. Updated only during the REVEAL screen (next class day). Never updated immediately after a choice is committed.

| Stat | Icon | What it tracks |
|---|---|---|
| Power Reserves | ⚡ | Energy available. Depleted by scanning, investigation, repairs. |
| Hull Integrity | 🛡 | Structural health. Damaged by bad decisions about physical forces. |
| Data Collected | 📡 | Scientific findings. Grows with good investigative choices. |
| Crew Morale | 👥 | Team wellbeing. Affected by repeated bad outcomes. |

**Warning threshold:** Any stat below 30% — GAIA flags it, some options become restricted.
**Crisis threshold:** Any stat hits 0%, or two stats below 20% simultaneously — triggers crisis episode.
**Failure system:** Three tiers. First failure = debrief + checkpoint reset. Second failure = choices restricted. Third failure = GAIA narrows to only 2 options with dry commentary.

---

## THE DAILY CLASSROOM FLOW

Four phases, always in this order, never changes (important for neurodiverse students):

1. **Scenario** — GAIA narrates, story advances, today's situation introduced
2. **Exit Ticket** — Students complete individual Google Form CER (Claim/Evidence/Reasoning). Timer used here. Only on CHOICE days. Lesson/graph days use this phase for reading time.
3. **Discussion** — Class debates using their evidence. Timer used here too.
4. **Final Vote** — Official class decision. Choices only selectable in this phase.

**After vote:** Commit → Processing screen (GAIA says "you'll find out next class") → Save → Home.
**Next class:** Launch → auto-routes to REVEAL screen → stats update live → proceed to mission.

**Timer:** One flexible countdown. Teacher sets minutes fresh each day. Add-time buttons (+2min, +5min). Used for exit ticket phase AND discussion phase separately. No automation — teacher controls everything.

---

## PACING STRUCTURE

**School:** Higley Unified School District, Arizona. Starts mid-July.
**Period length:** ~40 minutes. Short days (Wednesdays) ~30 minutes.
**Textbook:** Savvas Realize / Elevate Science. No "chapters" — only Topics and Lessons.

**Day types:**
- `choice` — Full four-phase flow with vote
- `deepen` — Reading/lesson support day, no vote, phases 2-3 become reading timer
- `graph` — Data literacy day, no vote, graphs rendered as SVG in the app
- `climax` — Act finale, no vote

**Short day rule:** Graph days and deepen days are the best Wednesday options. Always include a `shortDayNote` in graph day content.

---

## GRAPH PROGRESSION (IMPORTANT — DO NOT REGRESS)

| Act 1 Day 3 | Bar graphs introduced — reading and comparing categories |
| Act 1 Day 7 | Bar vs. line comparison — which graph tells the story better? |
| Act 2 | Line graphs deepened — reading trends, making predictions from slope |
| Act 3 | Line graphs + "which graph fits this data?" decision |
| Act 4 | Introduce pie charts (parts of a whole) |
| Campaign 2+ | Scatter plots, stem and leaf, box and whisker |

**Current level:** Students know bar graphs and have compared bar vs. line. Act 2 deepens line graph skills. Never go backwards.

---

## CURRICULUM MAP

**District:** Higley Unified, Arizona. Standards are Arizona Science Standards.

### CAMPAIGN 1: The Prometheus Drift (Physical Science)

| Act | Topic | Standard | Weeks | Status |
|---|---|---|---|---|
| Act 1 | Atoms & Molecules | 6.P1U1.3 | 2 | ✅ COMPLETE |
| Act 2 | Kinetic Theory / States of Matter / Changes of State | 6.P1U1.1 + 6.P1U1.2 | 4 | ⬜ NEXT |
| Act 3 | Energy (Kinetic & Potential) | 6.P4U2.5 | 2 | ⬜ |
| Act 5 | Resolution | Synthesis | 1 | ⬜ |

### CAMPAIGN 2: The Lighthouse at the Edge of the Solar System (Earth & Space)
Gravity, Rotation/Revolution, Seasons, Moon Phases, Solar System Scale, Greenhouse Effect.
Stats: Navigation Accuracy, Solar Power, Signal Clarity, Earth Status.

### CAMPAIGN 3: The Vanishing (Life Science)
Ecosystems, Food Webs, Human Impact, Biodiversity.
Stats: Biodiversity Index, Water Quality, Food Supply Stability, Community Trust.

---

## ACT 2 CONTENT NEEDED

**Acts covered:** Kinetic Theory + States of Matter + Changes of State
**Standard:** 6.P1U1.1 (Kinetic Theory) + 6.P1U1.2 (State Changes)
**Weeks:** 4 weeks = ~20 days (but use 10 days per sub-act or combine into one 20-day act)

### Savvas Topic 1, Lesson 1 — States of Matter
- Guiding questions: What are the similarities and differences between solids, liquids, and gases? What is the relationship between particle motion and state of matter?
- Vocab: solid, liquid, surface tension, viscosity, gas
- Academic vocab: vibrate

### Savvas Topic 1, Lesson 2 — Changes of State
- Guiding questions: How does thermal energy play a role in particle motion and changes of state? What happens to particles during changes of state? How does pressure affect the change from liquid to gas?
- Vocab: thermal energy, temperature, melting point, freezing point, boiling point, evaporation, condensation, sublimation

**Story hook:** The temperature anomaly GAIA flagged in Act 1. Near absolute zero in Section C. Extreme heat in Section F. Same ship, same power source. Something is controlling particle speed. Act 2 is about figuring out what — and surviving it.

---

## HOW TO ADD NEW ACT CONTENT

The HTML file has clearly marked drop zones. Find this comment:

```
// ACT 2 CONTENT — DROP ZONE
```

Replace the placeholder object there with the full act content object.

### Content object structure:
```javascript
{
  id: 2,
  label: 'Act 2 · Kinetic Theory',
  standard: '6.P1U1.1',
  days: [
    {
      day: 1,
      type: 'choice',        // choice | deepen | graph | climax
      isReveal: false,       // true if this day opens with yesterday's consequence
      actLabel: 'Act 2 · Kinetic Theory',
      actTitle: 'Day title here',
      gaia: 'GAIA narration — use <em>italics</em> for emphasis',
      scenario: 'Story text shown to class. Use \\n for paragraph breaks.',
      exitTicketPrompt: 'What goes on Phase 2 screen (choice days only)',
      discussionPrompt: 'What goes on Phase 3 screen (choice days only)',
      choices: [
        {
          letter: 'A',
          text: 'The choice text',
          subtext: 'Smaller clarifying text below',
          deltas: { power: -5, hull: 0, data: 12, morale: 3 },
          branch: 'A-branchname',
          consequence: 'What GAIA says on the reveal screen next class'
        }
      ]
    },
    {
      day: 2,
      type: 'deepen',
      isReveal: true,
      actLabel: 'Act 2 · Kinetic Theory',
      actTitle: 'Day title',
      gaia: 'GAIA narration',
      scenario: 'Story text',
      readingFocus: 'Savvas Topic X, Lesson Y — description',
      gaiaReadingPrompt: '"GAIA line directing crew to read. Use quotes."',
      vocabFocus: ['word1', 'word2', 'word3'],
      noChoice: true,
      bridgeToNext: 'One sentence teasing what comes next class'
    },
    {
      day: 3,
      type: 'graph',
      isReveal: false,
      actLabel: 'Act 2 · Kinetic Theory',
      actTitle: 'Day title',
      gaia: 'GAIA narration introducing the graph',
      scenario: 'Context for the graph',
      graphData: {
        title: 'Graph title',
        // For bar graph:
        xLabel: 'X axis label',
        yLabel: 'Y axis label',
        bars: [
          { label: 'Bar 1', value: 85, status: 'safe' },    // safe|caution|warning|danger
          { label: 'Bar 2', value: 42, status: 'warning' }
        ],
        // For line graph (use data instead of bars):
        // data: [
        //   { label: 'Month 1', value: -12 },
        //   { label: 'Month 2', value: -28 }
        // ]
      },
      gaiaGraphNote: '"GAIA comment on what the graph shows or what graph type means"',
      graphQuestions: [
        '1. First question',
        '2. Second question',
        '3. Third question'
      ],
      shortDayNote: 'Short day (30 min): do questions 1 and 2 only.',
      noChoice: true
    }
  ]
}
```

---

## WHAT NOT TO CHANGE

- The engine code (everything except the CONTENT object)
- The stat system logic
- The four-phase flow
- The timer behavior
- The reveal/processing screen flow
- GAIA's name or core personality

---

## CROSS-CURRICULAR CONNECTIONS TO BUILD IN

- **Math:** Graph literacy (see progression above). Ratios and proportions in Campaign 2.
- **Ancient Civs (Social Studies):** Resource scarcity decisions mirror ancient civilization challenges. Simple machines (Campaign 1 Act 3 energy) connect to how ancients built structures.
- **ELA:** CER framework (Claim/Evidence/Reasoning) used every choice day as exit ticket.

---

## FILES IN THIS PROJECT

| File | Purpose |
|---|---|
| `PrometheusDrift.html` | Campaign 1 — Physical Science (active) |
| `Lighthouse.html` | Campaign 2 — Earth & Space (not yet built) |
| `Vanishing.html` | Campaign 3 — Life Science (not yet built) |
| `HANDOFF.md` | This document |

---

## QUICK REFERENCE — GAIA VOICE EXAMPLES

✓ "I have been hoping someone would come. I have a great deal of data and nowhere useful to send it."
✓ "Interesting decision. I'm sure that'll work out fine. Updating damage report now."
✓ "Physical properties include more than what the eye can detect."
✓ "A hypothesis without sufficient evidence is just a story."
✓ "I will know if you skipped them."
✓ "No pun intended. Actually, pun very much intended."

✗ Don't make GAIA panic
✗ Don't make GAIA condescending
✗ Don't make GAIA explain things the kids should figure out
✗ Don't use exclamation points in GAIA's voice
