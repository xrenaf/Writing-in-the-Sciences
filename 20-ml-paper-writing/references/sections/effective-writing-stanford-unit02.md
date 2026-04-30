# Stanford "Writing in the Sciences" — Unit 2: Verbs

Distilled from Kristin Sainani's Stanford course (notes by quanghuy0497, MIT-licensed), reframed for ML paper writing. Pairs with Unit 1 (clutter) and Unit 3 (sentence + paragraph).

## 1. Active voice

- Active voice is the natural way to talk and write. Passive voice is often a way to avoid claiming responsibility.
- To convert: ask **"WHO does what to whom?"** and put the WHO first.
- Advantages:
  - **Author responsibility** — keeps it visible that humans made choices.
  - **Readability** — more direct.
  - **Reduced ambiguity** — fewer dangling agents.
- Use passive **sparingly and purposefully**, e.g. in Methods when *what was done* matters more than *who did it*: "The model was trained for 100k steps."

## 2. Personal pronouns ("we" / "I")

- Avoiding "we" does **not** make science more objective — it just makes prose flabby.
- "We" claims responsibility for the assertion.
- The goal is **to be more objective**, not to **appear** more objective.
- For ML papers: "We propose" / "We find" / "We show" are correct and expected at every top venue.

### Active voice practice (from the course)

| Passive | Active |
|---|---|
| A recommendation was made by the DSMB committee that the study be halted. | The DSMB committee recommended halting the study. |
| Major differences in the reaction times of the two study subjects were found. | The two study subjects differed in reaction time. |
| It was concluded by the editors that the data had been falsified by the authors. | The editors concluded the authors falsified their data. |
| The first visible-light snapshot of a planet circling another star has been taken by NASA's Hubble Space Telescope. | NASA's Hubble Space Telescope took the first visible-light snapshot of a planet circling another star. |

## 3. Write with verbs

**Verbs make sentences go.** Compare:

> Loud music *came* from speakers embedded in the walls, and the entire arena *moved* as the hungry crowd *got* to its feet.

> Loud music *exploded* from speakers embedded in the walls, and the entire arena *shook* as the hungry crowd *leaped* to its feet.

### Use strong verbs

- **Pick a verb that already contains the adverb.** "approximately reports" → "estimates"; "thinks about the future" → "projects".
- **Use `to be` verbs sparingly.** They are the single most overused verbs in scientific writing. Substitute when possible:
  - *He is a student who is intelligent and confident.* → *The intelligent, confident student…*
- **Common nominalization fixes** (the verb is hiding inside a noun):

| Weak (verb-as-noun) | Strong |
|---|---|
| obtain estimates of | estimate |
| has seen an expansion in | expand |
| provides a methodologic emphasis on | emphasizes |
| offer confirmation of | confirm |
| perform an analysis of | analyze |
| conduct an evaluation of | evaluate |
| make a comparison between | compare |

### Don't bury the main verb

Keep subject and main verb close together at the start of the sentence. If a long modifier separates them, move it.

- ❌ *One study of 1,000 patients across 12 hospitals over 5 years found that…*
- ✅ *One study found that, across 1,000 patients in 12 hospitals over 5 years,…*

## 4. Practice rewrites (calibration set)

| Before | After |
|---|---|
| Review of each center's progress in recruitment is important to ensure that the cost involved in maintaining each center's participation is worthwhile. | We should review each center's recruitment progress to ensure its participation remains cost-effective. |
| It should be emphasized that these proportions generally are not the result of significant increases in moderate and severe injuries, but in many instances reflect mildly injured persons not being seen at a hospital. | These shifting proportions likely reflect stricter hospital admission criteria, not real increases in moderate and severe injuries. |
| There are multiple other mechanisms that are important, but most of them are suspected to only have a small impact… | Most other mechanisms play only a small role or act through one of the three primary mechanisms. |
| After rejecting paths with poor signal-to-noise ratios, we were left with 678 velocity measurements of waves with 7.5 seconds period and 891 measurements of 15-second waves. | Rejecting low-SNR paths left 678 velocity measurements of 7.5-second waves and 891 of 15-second waves. |

## 5. Grammar tips that catch ML reviewers' attention

- **`data` is plural**: "data **are**", not "data is".
- **affect vs. effect**: `affect` = verb (to influence); `effect` = noun (the influence). ("The class affected her" vs. "The class had an effect on her.")
- **compared to vs. compared with**: `compared to` highlights similarities between *different* things; `compared with` highlights differences between *similar* things. ML papers almost always want **compared with**.
- **that vs. which**:
  - `that` introduces an essential (restrictive) clause — no comma. *"The vial that contained her RNA was lost."* (identifies which vial)
  - `which` introduces a non-essential (non-restrictive) clause — set off by commas. *"The vial, which contained her RNA, was lost."* (only one vial)
- **Singular antecedents**: don't use "they/their" with a singular subject if it can be avoided — pluralize instead. *"Each student worries about their grade"* → *"All students worry about their grades."*
- **Hedge words** ("no appreciable change", "it is suspected that", "may suggest") are usually unnecessary and raise questions. Cut them unless you genuinely mean to hedge.

> *"Careful writers, watchful for small conveniences, go which-hunting, remove the defining whiches, and by doing so improve their work."* — Strunk & White

## How to use this in the ml-paper-writing workflow

- Run the strong-verb pass after the §H clutter pass. The two together typically fix 80% of the prose-level issues in a draft.
- For Methods sections in ML papers, do a focused **nominalization sweep**: search for "performed", "conducted", "made", "obtained", "carried out" — most can be replaced with a single strong verb.
- For Abstracts: confirm that every sentence is in active voice unless you have a specific reason for passive.

---

*Source: Kristin Sainani, "Writing in the Sciences" (Stanford Online). Notes by [quanghuy0497](https://github.com/quanghuy0497/Writing-in-the-Science_Stanford), MIT License. Adapted for ML paper writing.*
