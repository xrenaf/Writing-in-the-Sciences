# Paragraph Density — MMLongBench Exemplar

## Why This Reference Exists

A common failure mode in ML drafts is the **thin analysis paragraph**: a topic
sentence, one supporting number, one hedge, and a period. These paragraphs look
tidy but carry one claim where a reviewer expects three. They read as notes,
not as analysis, and they leave the reader unsure what the finding actually is.

Reviewers at top ML venues (NeurIPS, ICML, ICLR) expect each analytical
paragraph to carry (i) the claim, (ii) specific numerical evidence, (iii)
corroborating cases, (iv) a mechanism or causal reading, and (v) a scoped
limitation or open question. A three-sentence paragraph cannot do all five.

**Rule of thumb:** an analysis paragraph should run **100–200 words** (roughly
6–10 substantive sentences, each carrying new content). A method paragraph
should run **150–250 words**. A Related Work paragraph should run **180–250
words** and compare multiple prior lines inline. Anything shorter than 80 words
in the body of a paper should trigger a "is this really a paragraph, or a
fragment that belongs elsewhere?" check.

The exemplar for this reference is Wang et al.,
*MMLongBench: Benchmarking Long-Context Vision-Language Models Effectively and
Thoroughly* (NeurIPS 2025, arXiv:2505.10610). It is a benchmark paper — the
same genre as most of the user's work — and its paragraphs illustrate each of
the three use cases below at publication quality.

---

## Exemplar 1 — Analysis paragraph (§4.1, bolded-claim pattern)

Verbatim quote from MMLongBench §4.1 "All models struggle, but closed-source
models perform better":

> **Models can generalize to longer context lengths.** Another interesting
> observation is that some models can generalize to longer context lengths
> than they are officially designed for. For example, although the context
> window for Qwen2-VL-72B during training is only 32K tokens, the model can
> generalize to a 128K input length and still achieve an average score of
> 51.9. We also observe similar effects on other models, such as Ovis2-34B and
> InternVL2.5-26B. This phenomenon is likely because the underlying LLMs of
> those LCVLMs have been trained with longer context windows [29]. We leave
> further investigation to future work.

**Structure decoded:**

| Sentence | Function | What it adds |
|---|---|---|
| S1 (bold) | Claim header | One-sentence summary of the finding |
| S2 | Scope restatement | Clarifies *which* models, so reader doesn't generalize too far |
| S3 | Numerical example | Qwen2-VL-72B, 32K train → 128K inference, score 51.9 |
| S4 | Corroborating cases | Named additional models (Ovis2-34B, InternVL2.5-26B) |
| S5 | Mechanism + citation | Proposed causal reading, backed by [29] |
| S6 | Honest limitation | "Leave further investigation to future work" |

That is a six-move paragraph in 76 words. Every sentence has a distinct job;
none is filler. A thin version of the same paragraph would stop after S3
("Qwen2-VL-72B generalizes from 32K to 128K at score 51.9.") and leave the
reader unsure whether this is a one-off or a pattern.

---

## Exemplar 2 — Method paragraph (§3.1, dense design-choice pattern)

Verbatim quote from MMLongBench §3.1 on the VRAG task:

> **Visual retrieval-augmented generation (VRAG)** evaluates an LCVLM's
> ability to ground on relevant information retrieved from a large corpus,
> while filtering out distractors and irrelevant content. To evaluate this
> capability, we use factual knowledge-based VQA as a representative task.
> This task requires answering questions about the named entity identified in
> an image, such as "Who designed the building in this picture?" We include
> InfoSeek [22] and ViQuAE [23] in this category. To build a long context, we
> insert the gold passage(s) (the passage with the answer) among a large set
> of distracting passages retrieved from Wikipedia. For ViQuAE, we use gold
> passages from KILT [72] since it is constructed upon TriviaQA [73]. For
> InfoSeek, we choose the lead section of the named entity's Wikipedia page
> as the gold reference and remove all examples for which the answer cannot
> be found in the lead section. Then, we split Wikipedia pages into 100-word
> passages and incrementally add retrieved passages that do not contain the
> answer or the named entity as distractors until we reach the given input
> length L. For retrieval, we use the named entity instead of the image
> itself as the query, because text-based retrieval achieves higher recall
> and provides harder distractors. In ViQuAE, each example contains a single
> gold passage, and we insert it at six evenly distributed positions, while
> in InfoSeek, the lead sections often contain hundreds of words, resulting
> in multiple passages. We randomly shuffle them into three permutations. We
> use the substring exact match (SubEM) as the metric, following previous
> work [74]. See more details in Section A.1.

**Structure decoded:** 220 words, 11 substantive sentences, covering:
capability definition → task framing → example question → dataset sources →
context construction recipe → per-dataset handling → design tradeoff (why
entity not image as query) → per-dataset instantiation → metric + citation →
appendix pointer.

Every design choice is justified inline. There is no "as detailed in the
appendix, we do X" — the reasoning is visible in the main text, so a reviewer
who never opens the appendix still understands *why* each decision was made.

---

## Exemplar 3 — Related Work paragraph (§2, methodological organization)

Verbatim quote from MMLongBench §2 "Long-context benchmarks":

> **Long-context benchmarks.** Needle-in-a-haystack (NIAH) [56] is one of the
> first commonly adopted tasks to evaluate the text-pure long context ability
> of LLMs, as it can be procedurally generated with arbitrarily long lengths
> and needle position [57]. This task inserts a "needle" at specific depths
> of a long essay and tests models' ability to recall it. Recent works have
> also extended the NIAH task to more complex versions [58–60]. However,
> several benchmarks [12, 20] discover that using a single NIAH task only
> partially reflects LLMs' overall long-context ability. As a result,
> numerous benchmarks with broad coverage of diverse downstream applications
> have been constructed [12, 14, 20, 61–64] to provide a comprehensive
> evaluation.

**Structure decoded:** 99 words, 5 sentences — each citing different prior
work, building a chronological-then-critical arc: (1) origin + citation,
(2) mechanism, (3) extensions, (4) critique of the paradigm, (5) response of
the field. No paper is discussed in isolation; each citation exists to
support a *direction* of the argument. That is the Lipton–Steinhardt rule for
Related Work ("one line of work uses X, whereas we use Y") applied paragraph
by paragraph.

---

## The Density Checklist

Before declaring any body paragraph done, check that it contains at least
**five** of the following:

1. A claim sentence (usually first, often bolded for analysis paragraphs).
2. A specific numerical datapoint with units/context (e.g., "51.9 at 128K",
   not "high accuracy").
3. A named concrete case (model name, dataset name, subtype name) — not a
   generic "some models".
4. At least one additional corroborating case, to rule out a one-off.
5. A mechanism sentence — why the effect happens, not just that it happens.
6. A comparison to an alternative or baseline, inline.
7. A scoped limitation, caveat, or future-work pointer.
8. A citation to prior work when the claim borrows from or contrasts with it.

Fewer than five of the eight usually means the paragraph is a note, not an
argument. Either fold it into an adjacent paragraph or expand it with the
missing ingredients.

---

## Three Paragraph Patterns (apply by use case)

### Pattern A — Analysis paragraph (§5 / §4 in most ML papers)

```
[Bold topic claim.] [Scope restatement.] [Specific numerical example with
names.] [One or two corroborating cases.] [Mechanism or causal reading, with
citation if borrowed.] [Honest caveat or "leave to future work".]
```

Length target: **80–160 words**, 6–8 substantive sentences. If an analysis
paragraph runs under 60 words, it is almost certainly missing the mechanism
or the corroborating case.

### Pattern B — Method design paragraph (§3)

```
[Capability or module definition.] [Task / design framing.] [Concrete
example or input–output spec.] [Dataset sources with citations.]
[Construction recipe step-by-step.] [At least one design-choice justification
("we use X because…").] [Metric + citation.] [Appendix pointer for
low-level details only.]
```

Length target: **150–250 words** per module. Every design knob mentioned
gets a because-clause in the same paragraph. If a reviewer has to flip to
the appendix to learn *why*, the paragraph is under-written.

### Pattern C — Related Work methodological paragraph (§2)

```
[Topic sentence naming one line of prior work.] [Origin + citation.]
[Mechanism.] [Extensions with citations.] [Critique or limitation of the
paradigm.] [Field response with citations.] [Transition to our work OR
contrast with our work.]
```

Length target: **180–250 words**. Organize by *direction of argument*, not
paper by paper. Every citation exists to support a move in the argument.

---

## Anti-Patterns (thin-paragraph smells)

- **The orphan finding.** "Model X scores 58.68\% at 32K and 45.50\% at 128K,
  a 13.18 pp drop." → Missing mechanism, missing corroboration, missing
  caveat. Expand to: *why* does X drop more than Y? which other models show
  the same pattern? is the drop statistically stable?
- **The generic "some models".** "Some models degrade sharply at longer
  context." → Name them, with scores. Generic quantifiers are not analysis.
- **The buried mechanism.** Mechanism explanation is relegated to a single
  parenthetical. Expand it into a full sentence with a citation where
  possible.
- **The dangling caveat.** Paragraph ends on the finding with no honest
  scoping. Reviewers will supply the scoping themselves (badly) unless you
  do.
- **Paragraph-as-bullet.** Three-sentence paragraphs in a row read as a
  bullet list misformatted as prose. Either use a real `itemize` block
  (acceptable in contribution lists) or expand each into a real paragraph.

---

## Application Workflow

When you suspect a paragraph is thin:

1. Identify the claim (the sentence the paragraph is trying to defend).
2. Ask the eight density-checklist questions. Note which are missing.
3. For each missing element, look into the result CSVs, the source report,
   or the related-work notes for content that would fill it.
4. Rewrite the paragraph with Pattern A / B / C as scaffold. Target the
   length range for the paragraph's use case.
5. Run the five-dimension self-review (§E of SKILL.md): contribution,
   clarity, experimental strength, evaluation completeness, method
   soundness.

Do *not* inflate with hedge words, transitions, or rephrasings. Density
means more *content*, not more words. A 160-word paragraph with seven
substantive moves beats a 200-word paragraph with three moves and a lot of
"importantly", "notably", "it should be noted that".

---

## Source

- Wang, Z., Yu, W., Ren, X., Zhang, J., Zhao, Y., Saxena, R., Cheng, L.,
  Wong, G., See, S., Minervini, P., Song, Y., Steedman, M.
  *MMLongBench: Benchmarking Long-Context Vision-Language Models
  Effectively and Thoroughly.* NeurIPS 2025.
  arXiv:2505.10610. https://arxiv.org/abs/2505.10610

All three quoted paragraphs are from the v3 (2025-10-06) arXiv version.
