# Stanford "Writing in the Sciences" — Unit 3: Sentence and Paragraph

Distilled from Kristin Sainani's Stanford course (notes by quanghuy0497, MIT-licensed), reframed for ML paper writing. This is the most directly applicable unit for paragraph-level craft in §A–C of the SKILL.md.

---

## Part I — The Sentence

### 1. Punctuation (in increasing power to separate)

```
comma  →  colon  →  dash  →  parentheses  →  semicolon  →  period
```

In increasing **formality**:

```
dash  →  parentheses  →  others (comma, colon, semicolon)
```

#### Semicolon `;`

- **Joins two independent clauses** that are closely related: *"He knew something about the world; he also cared about it."*
- **Separates list items that contain internal commas**: *"…because people organized and voted; because leaders enacted smart, forward-looking policies; because perspectives opened up."*

#### Parentheses `( )`

- Insert an **afterthought or explanation** that the sentence does not need to remain grammatical. The reader should be able to skip the parenthetical without losing the main point. (This sentence is itself an example.)

#### Colon `:`

- Introduce a **list, quote, explanation, conclusion, or amplification**.
  - *"The hydrogen bonds are made as follows: purine position 1 to pyrimidine position 1; …"* — list.
  - *"That's one reason I'm so optimistic about the future: the constant churn of scientific progress."* — explanation.
- **Join two independent clauses** when the second amplifies or extends the first. The first clause sets up the second.

#### Dash `—` (`---` in LaTeX)

- Adds **emphasis** or inserts a strong, abrupt definition or aside almost anywhere in a sentence. Don't overuse it — it loses impact.
- *"The drugs did more than prevent new fat accumulation. They also triggered overweight mice to shed significant amounts of fat — up to half their body weight."*
- **Note**: dashes legitimately let you violate the "don't bury the verb" rule, because the reader finds the verb just after the punctuation.

> *"A dash is a mark of separation stronger than a comma, less formal than a colon, and more relaxed than parentheses."* — The Elements of Style

### 2. Parallelism

**Pairs of ideas** joined by `and`, `or`, `but` — and **lists of ideas** — must be in parallel grammatical form. Pick a structure (verb / infinitive / noun phrase) and **stick to it**.

- ❌ *"NASA's rover flew 354 million miles, blasted through the atmosphere, deployed a parachute, unfurled a sky crane, and a gentle landing on Mars."*
- ✅ *"…flew 354 million miles, blasted through the atmosphere, deployed a parachute, unfurled a sky crane, and touched down gently on Mars."* (all past-tense verbs)

Examples:

| Non-parallel | Parallel |
|---|---|
| If you want to be a good doctor, you must study hard, critically think about the medical literature, and you should be a good listener. | If you want to be a good doctor, you must study hard, listen well, and think critically about the medical literature. |
| This research follows four phases: (1) establishing instruments, (2) pattern measurement, (3) developing interventions, and (4) the dissemination of successful interventions. | This research follows four phases: (1) establishing instruments, (2) measuring patterns, (3) developing interventions, and (4) disseminating successful interventions. |

Parallelism is doubly important in **ML paper bullet contributions** — every contribution bullet in the introduction should start the same way (e.g., "We propose…", "We show…", "We release…").

---

## Part II — The Paragraph

### 3. Paragraph principles

- **One paragraph = one idea.** This is identical to §A "one paragraph, one message" in SKILL.md and is *the* most-violated rule in ML papers.
- **Keep paragraphs short.** White space helps reading; long paragraphs feel tedious and bury the point.
- **Give away the punch line early.** State the main claim in the first sentence (topic sentence), then support it.
- **The first and last sentences are remembered best.** Engineer them.
- **Logical flow types** to choose from:
  - Sequential in time
  - General → specific
  - Logical argument: *"if a then b; a, therefore b"*
- **Paragraph flow comes from**:
  1. logical ordering of ideas,
  2. **parallel sentence structure** between consecutive sentences,
  3. *minimal* transition words — only when actually needed.

### Exemplary paragraph (Obama on science)

> *"This kind of progress hasn't happened on its own. It happened because people organized and voted for better prospects; because leaders enacted smart, forward-looking policies; because people's perspectives opened up, and with them, societies did too. **But this progress also happened because we scienced the heck out of our challenges. Science is how we were able to combat acid rain and the AIDS epidemic.** Technology is what allowed us to communicate across oceans and empathize with one another when a wall came down in Berlin or a TV personality came out. Without Norman Borlaug's wheat, we could not feed the world's hungry. Without Grace Hopper's code, we might still be analyzing data with pencil and paper."*

What makes it work:
- Only **one** transition word ("But").
- The main idea sits in the **middle**, framed by setup before and amplification after.
- General → specific.
- Heavy use of **parallel structure** ("Science is how…", "Technology is what…"; "Without Borlaug's wheat…", "Without Hopper's code…") — this is what creates the rhythm without needing connective tissue.

### 4. Paragraph editing — the workflow

Both editing examples in the source go through the same procedure, which is the right one to use on any ML paragraph that "feels off":

1. **Outline first.** Write down the main idea and the 2–4 supporting points in plain English.
2. **Reorder** points until they form a clean *general → specific* (or chronological / logical) progression.
3. **Strike** anything that does not advance the main idea.
4. **Re-write** following the reordered outline, using parallel structure where you can.

### Editing example (compressed)

**Before (212 words):** A meandering paragraph about whether perfume concentrations in an experiment were appropriate.

**Outline:**
- *Main idea*: were the concentrations appropriate?
- *Point 1*: too-high concentrations distort quality ratings → handled by standardizing intensity.
- *Point 2*: appropriate if they produce variability in ratings → true for most scents, with two exceptions.

**After (91 words):**
> Perfume intensity and quality are negatively correlated at high concentrations: if the scent is too strong, people rate it unfavorably. We therefore set each ingredient's concentration to match the intensity of a reference scent (1-butanol). The resulting concentrations appeared appropriate for most scents, since participants' preferences varied along the 0–10 scale. However, participants largely agreed on bergamot (highest ratings) and vetiver (lowest), so different concentrations may have been needed for these two.

**That is more than a 50% length cut at zero information loss** — purely from outlining first.

### 5. A few more tips

- **Repetition**: before reaching for a thesaurus, ask
  1. Is the second instance even necessary?
  2. If yes, is a synonym *really* better than just repeating the word?
  Often the repeat is fine. **Keywords must be repeated** — switching to a synonym makes the reader think you mean a different concept.
- **Acronyms**: don't abbreviate just because a word recurs. Only use standard, well-known acronyms. Define them once per major section in long papers.
- **Transition words can't fix bad logic.** Professional writers mostly use only `and`/`or` (additional information) and `but`/`however` (changing gear). If you need "moreover, furthermore, additionally" to glue a paragraph together, the underlying flow is broken — fix that, not the transitions.
- **The Rule of Three.** Three is the pleasing number for lists and examples — enough to make a point, not so many it overwhelms. *"Veni, vidi, vici."* / *"of the people, by the people, for the people."* When in doubt, pick three.

---

## How to use this in the ml-paper-writing workflow

- This unit operationalizes the §A–C paragraph craft block in SKILL.md. The "outline first" editing workflow in §4 above is exactly what to do when a paragraph fails the §A clarity check.
- For ML papers specifically:
  - Use **parallelism** ruthlessly in contribution bullets (Intro), table rows, and ablation lists.
  - Use **dashes** sparingly but deliberately for emphasis in Abstracts and conclusion paragraphs — they punch through dense prose.
  - Apply the **"give away the punch line early"** rule to every Experiments paragraph: state the finding in sentence 1, then describe the setup.
  - Apply the **rule of three** to contribution bullets and to the number of baselines highlighted in the headline table (you can compare against 10, but emphasize 3).

---

*Source: Kristin Sainani, "Writing in the Sciences" (Stanford Online). Notes by [quanghuy0497](https://github.com/quanghuy0497/Writing-in-the-Science_Stanford), MIT License. Adapted for ML paper writing.*
