# Stanford "Writing in the Sciences" — Unit 1: Principles of Effective Writing

Distilled for the ml-paper-writing skill from Kristin Sainani's Stanford course (notes by quanghuy0497, MIT-licensed). Use this when polishing prose at the sentence level — it pairs naturally with Gopen & Swan's 7 principles and Ethan Perez's micro-tips already in `references/writing-guide.md`.

## 1. What "good writing" actually means

- **Goal**: communicate an idea **clearly and effectively**. Elegance is secondary.
- For every sentence ask: *Is this easy to understand? Is this enjoyable to read?*
- **Verbs move sentences forward; nouns slow them down.**

## 2. The five principles

1. **Cut unnecessary words and phrases.** Learn to part with your words.
2. **Use the active voice**, not the passive. ("We trained X" beats "X was trained.")
3. **Use strong verbs.** Concrete verbs carry meaning; weak verbs (`be`, `make`, `do`, `have`) bury it.
4. **Do not turn verbs into nouns** (nominalization). `analyze` > `perform an analysis`; `decide` > `make a decision`.
5. **Do not bury the main verb.** Keep subject and verb close together; defer subordinate clauses to the end.

### Worked example (from the course)

> *Dysregulation of physiologic microRNA (miR) activity has been shown to play an important role in tumor initiation and progression, including gliomagenesis. Therefore, molecular species that can regulate miR activity on their target RNAs without affecting the expression of relevant mature miRs may play equally relevant roles in cancer.*

Diagnosed problems:
- Nominalizations: `dysregulation`, `initiation`, `progression`, `expression`.
- Vague nouns: `physiologic`, `molecular species`.
- Unnecessary jargon/acronym: `miR`, `gliomagenesis`.
- Passive voice: `has been shown`.
- Subject `molecular species` is far from main verb `may play`.

Rewrite:
> *Changes in microRNA expression play a role in cancer, including glioma. Therefore, events that disrupt microRNAs from binding to their target RNAs may also promote cancer.*

## 3. Clutter to cut

| Category | Examples |
|---|---|
| **Dead phrases** | "as is well known", "as has been shown", "it can be regarded that", "it should be emphasized that" |
| **Empty words** | "important", "methodologic", "basic tenets of", "interesting" |
| **Long words for short** | "utilize" → use; "in order to" → to; "due to the fact that" → because |
| **Unnecessary jargon / acronyms** | Any acronym used fewer than 3 times; any term the target reviewer would not already know |
| **Repeated meaning** | "studies and examples", "challenges and difficulties", "successful solutions" (a solution is already successful) |
| **Adverbs as crutches** | "very", "really", "quite", "basically", "generally", "actually" — fine for speech, weak in writing |

## 4. Three small tricks

### A. Eliminate the negatives
Negatives force the reader to do extra mental arithmetic. Almost any negative can be flipped.

| Negative | Positive |
|---|---|
| not honest | dishonest |
| not harmful | safe |
| does not have | lacks |
| did not remember | forgot |
| did not pay attention to | ignored |
| did not succeed | failed |

- *I am not crazy about the movie but for its aesthetic elements.* → *I only like the movie's aesthetic elements.*
- *She did not want to perform the experiment incorrectly.* → *She wanted to perform the experiment correctly.*

### B. Eliminate "there is / there are / there was"
These constructions waste the verb slot on `to be`. Promote the real verb.

- *There are many ways in which we can arrange the pulleys.* → *We can arrange the pulleys in many ways.*
- *The data confirm that there is an association between vegetables and cancer.* → *The data confirm an association between vegetables and cancer.*

### C. Omit needless prepositions and "that"
Most "that"s and many prepositions can be deleted without losing meaning.

- *The meeting happened on Monday.* → *The meeting happened Monday.*
- *They agreed that it was true.* → *They agreed it was true.*

## 5. Practice rewrites (use as a calibration set)

| Before | After |
|---|---|
| Anti-inflammatory drugs may be protective for the occurrence of Alzheimer's Disease. | Anti-inflammatory drugs may protect against Alzheimer's Disease. |
| Clinical seizures have been estimated to occur in 0.5% to 2.3% of the neonatal population. | Clinical seizures occur in 0.5% to 2.3% of newborns. |
| Ultimately P53 guards not only against malignant transformation but also plays a role in developmental processes as diverse as aging, differentiation, and fertility. | Besides preventing cancer, P53 also plays a role in aging, differentiation, and fertility. |
| Injuries to the brain and spinal cord have long been known to be among the most devastating and expensive of all injuries to treat medically. | Brain and spinal cord damage are among the most devastating and expensive. |
| An IQ test measures an individual's abilities to perform functions that usually fall in the domains of verbal communication, reasoning, and performance on tasks that represent motor and spatial capabilities. | An IQ test measures an individual's verbal, reasoning, and motor-spatial capabilities. |
| As we can see from Figure 2, if the return kinetic energy is less than 3.2 Up, there will be two electron trajectories associated with this kinetic energy. | Figure 2 shows that return kinetic energy below 3.2 Up yields two electron trajectories. |

## How to use this in the ml-paper-writing workflow

- Run this checklist as the **last pass** on every Abstract and Introduction paragraph, after the paragraph clarity check (§A in SKILL.md) and reverse outlining (§B).
- For Methods and Experiments, focus on principles 3–5 (strong verbs, no nominalizations, no buried verbs) — these sections are where nominalization damage is worst in ML papers.
- When tightening to fit a page limit, the clutter table in §3 is usually worth 5–15% length reduction at zero information cost.

---

*Source: Kristin Sainani, "Writing in the Sciences" (Stanford Online). Notes by [quanghuy0497](https://github.com/quanghuy0497/Writing-in-the-Science_Stanford), MIT License. Adapted and re-framed for ML paper writing.*
