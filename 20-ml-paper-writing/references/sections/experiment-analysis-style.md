# Experimental Analysis Style: Conclusion-Driven, Not Number-Driven

This reference provides annotated examples from two published papers that
exemplify the conclusion-driven analysis style described in SKILL.md H.5.

The core failure to avoid: **number padding** — restating model-by-model
scores the reader can already see in the table. Every sentence in an
analysis paragraph must add value the table cannot provide: a conclusion,
a mechanism, a comparison, or a scoped caveat.

---

## The Five Rules (recap)

1. **Conclusion first.** The topic sentence IS the finding.
2. **Mechanism over numbers.** Explain WHY, not just WHAT.
3. **Numbers as anchors only.** One number to establish scale; never enumerate.
4. **Relative comparisons over absolute values.**
5. **Name the bottleneck.**

---

## Template A: Difficulty Ranking with Mechanism

Use when: comparing difficulty across categories, types, task topologies,
or dataset splits.

**Pattern:** `[difficulty claim] → [easiest + why] → [next + why] →
[hardest + why] → [subtype refinement] → [appendix pointer]`

### Example A-1: MC-Search — Topology-Specific Challenges

Source: MC-Search (NeurIPS 2025), Section 4.2

```latex
\paragraph{Topology-Specific Challenges.}
Across reasoning topologies, we observe \emph{Parallel Image-Text Fork}
is the most challenging, where all backbones reach their lowest F1 and
HPS. The difficulty comes from the need to plan and cover both text and
image branches simultaneously, so missing either branch directly lowers
HPS, and under the top-1 retrieval constraint models often fail to
capture the full evidence set. Aligning parallel evidence without strict
order further increases the risk of incomplete or inconsistent reasoning.
\emph{Multi-Images Fork} is also difficult, mainly due to the challenge
of aligning multiple visual evidences with corresponding textual facts,
where models often retrieve the right images but misattribute or fail to
integrate them coherently. In contrast, \emph{Text-Initiated} and
\emph{Text-Only Chains} are relatively easier, as they rely primarily on
text retrieval and linear reasoning, which align with model strengths.
\emph{Image-Initiated Chains} are also tractable: once the initial
visual step is correct, subsequent textual validation is linear and more
stable than multi-branch reasoning.
```

**Why this works:**
- Opens with conclusion (Parallel Image-Text Fork is hardest)
- Every category gets a 1-2 sentence mechanism ("difficulty comes from
  the need to plan and cover both branches")
- Zero model-by-model score enumeration
- Relative ordering via "most challenging" / "also difficult" / "easier"
  / "tractable" rather than absolute numbers
- Reader walks away understanding WHY each topology is hard

### Example A-2: MMLongBench — NIAH Challenge Analysis

Source: MMLongBench (NeurIPS 2025), Section 4.2

```latex
\noindent{\textbf{Text-image interleaved NIAH tasks are challenging.}}
In \cref{fig:vh_multi_difficulty}, we find that even state-of-the-art
models like GPT-4o and Gemini-2.5 struggle to surpass 80\% accuracy on
VH-Multi when the context length is just 8K tokens (approximately 22
images). Most models are just slightly better than a random guess (50\%).
This demonstrates that locating objects in a large set of images is still
hugely challenging for current LCVLMs. [...] We find that most models
achieve low performance on the counting and reasoning tasks, with scores
below 30 and 40, respectively. The difficulty of the tasks and low
performance result in poor separability between models. While the
retrieval is an easier task, it still does not align well with DocVQA
tasks. In short, we find that \emph{both VH and MM-NIAH present
significant challenges to current LCVLMs}, thus showing limited
differentiation between models and weak alignment with other tasks.
```

**Why this works:**
- Conclusion stated in the bold heading AND in the closing sentence
- Uses two numbers ("80%", "50%") only to establish scale (ceiling and
  chance level), not to compare models
- Explains the consequence ("poor separability") rather than listing scores
- Closes with a synthesized takeaway

---

## Template B: Bottleneck Identification / Error Analysis

Use when: explaining where models fail and what capability is missing.

**Pattern:** `[what fails most] → [mechanism] → [what fails less + why]
→ [synthesized bottleneck claim]`

### Example B-1: MC-Search — Error Taxonomy Synthesis

Source: MC-Search (NeurIPS 2025), Section 4.3

```latex
The most frequent errors are \emph{Retrieval-Failure} (84.7\%),
\emph{Hallucinated-Entity/Attribute} (75.8\%), and \emph{Step-Omission}
(74.3\%), revealing that current models often fail to ground reasoning in
relevant evidence, introduce unsupported content, or skip key steps.
Mid-frequency errors (e.g., modality mismatch, spurious steps) reflect
unstable planning, while structural errors (order/dependency mistakes,
multi-hop failures) are rarer but, given limited retrieval, remain
non-trivial for future study. Evidence misinterpretation is infrequent,
suggesting models can handle retrieved context; major failures arise
earlier, during planning and evidence acquisition. Overall, these
patterns [...] identify retrieval fidelity (modality-aware retrieval,
sufficient planning/hop coverage, and calibrated stopping) as the central
bottleneck for reliable chain-level reasoning.
```

**Why this works:**
- Uses three numbers to anchor the claim (top-3 error rates), then stops
- "Evidence misinterpretation is infrequent" — a conclusion, not a
  number — and immediately explains what this MEANS ("models can handle
  retrieved context; major failures arise earlier")
- Closes by naming the bottleneck ("retrieval fidelity") with three
  specific dimensions

### Example B-2: MMLongBench — Cross-Modal Bottleneck

Source: MMLongBench (NeurIPS 2025), Section 4.4

```latex
We also examine the sources of errors in the VRAG category in
\cref{fig:vrag_error_analysis}. Since \viquae is built on TriviaQA, we
replace all images in \viquae questions with their corresponding entity
names and feed those text-only questions into LCVLMs. All models show
varying degrees of improvement, with Gemma3-27B achieving the largest
gain of 26.4 points (at 128K), suggesting that \emph{a bottleneck of
LCVLMs lies in cross-modality information retrieval.} Besides, providing
entity names as input to corresponding LLMs improves model performance.
These results illustrate a common trade-off between multimodal and
text-only long-context abilities during the training of LCVLMs.
```

**Why this works:**
- One number (26.4 points) to anchor the largest effect; not listing
  every model
- The bottleneck is named explicitly in emphasis
- Closes with a higher-level takeaway (the training trade-off)

---

## Template C: Functional Relationship / Trend Analysis

Use when: analyzing how a continuous variable (context length, chain
length, retrieval depth) affects performance.

**Pattern:** `[overall trend claim] → [low end behavior + why] → [high
end behavior + why] → [which models are robust / fragile] → [takeaway]`

### Example C-1: MC-Search — Over- and Under-Retrieval

Source: MC-Search (NeurIPS 2025), Section 4.3

```latex
The results reveal that both extremes are harmful, though in different
ways. When models severely under-retrieve ($\Delta$Step $<-2$),
performance drops sharply as essential evidence is skipped, creating gaps
that later reasoning cannot recover. Conversely, moderate over-retrieval
($\Delta$Step $=1$--$2$) often improves accuracy [...], suggesting that
one or two extra turns can help recover from imperfect planning. However,
when over-retrieval is excessive ($\Delta$Step $\geq4$), noise and
irrelevant context lead to sharp drops across all models. Gemini-2.5-Pro
is most resilient [...] while Claude-3.7-Sonnet and GPT-4o-Mini are
highly vulnerable. This underscores a central tension between capturing
sufficient evidence and avoiding over-retrieval.
```

**Why this works:**
- Opens with the conclusion ("both extremes are harmful")
- Explains the mechanism at each end of the spectrum (under: evidence
  gaps; over: noise)
- Model names used only to illustrate the robustness spectrum, not to
  report scores
- Closes with the conceptual tension, not a number

---

## Template D: Model Specialization / Cross-Category Divergence

Use when: showing that different models excel at different tasks and no
single model dominates.

**Pattern:** `[no-single-winner claim] → [model A: strong X, weak Y] →
[model B: inverts] → [proxy / correlation insight] → [takeaway]`

### Example D-1: MMLongBench — Task-Dependent Strengths

Source: MMLongBench (NeurIPS 2025), Section 4.1

```latex
\noindent{\textbf{Different models exhibit different strengths.}}
Generally, we find that model performance varies considerably across
different tasks. For instance, Qwen2.5-VL-32B outperforms InternVL3-38B
on VRAG, but underperforms on NIAH. Similarly, Ovis2-34B excels at
summarization but struggles on DocVQA. These findings further support the
necessity of a comprehensive benchmark covering diverse downstream tasks.
```

**Why this works:**
- Two concrete contrastive examples (not ten)
- No scores cited — just "outperforms" / "underperforms" / "excels" / "struggles"
- Conclusion closes the paragraph (benchmark diversity is necessary)

### Example D-2: MMLongBench — Cross-Category Correlation

Source: MMLongBench (NeurIPS 2025), Section 4.3

```latex
We find that different categories do not consistently show strong
correlation ($<0.85$) with each other. Specifically, VRAG and NIAH
closely correlate because retrieval is the central capability of both
tasks. [...] Meanwhile, summarization and long-document VQA show a high
correlation of 0.88, likely due to their shared input format ---
image-based PDF documents. This suggests that image types affect category
correlations. In contrast, ICL tasks show relatively weak correlations
with other categories. The ICL tasks evaluate models' ability to induce
new classification rules from numerous exemplars, a skill orthogonal to
recalling facts in long contexts.
```

**Why this works:**
- States the finding first ("do not consistently show strong correlation")
- Uses one threshold ($<0.85$) and one number (0.88) to anchor claims —
  not a correlation matrix readout
- Explains WHY pairs correlate or not (shared retrieval capability,
  shared input format, orthogonal skill)
- Each pair gets a mechanism, not just a number

---

## Anti-Patterns (what to avoid)

### Anti-Pattern 1: Spreadsheet Narration

```
BAD: "GPT-4o achieves 62.9, Gemini-2.5-Pro achieves 71.3, Qwen2-VL-72B
achieves 51.9, InternVL2.5-26B achieves 44.2, and Ovis2-34B achieves
41.6. These results show that closed-source models perform better."
```

The entire paragraph adds nothing the table does not already show.

```
GOOD: "All models struggle on our vision-language long-context tasks,
with even the strongest closed-source model reaching only moderate
accuracy at 128K. Open-source models close the gap on specific tasks —
Ovis2-34B matches GPT-4o on summarization, and Qwen2.5-VL-32B surpasses
Gemini-2.0-Flash on VRAG — but no open-source model is consistently
competitive across all categories."
```

The rewrite names the conclusion, gives two contrastive examples to
bound the claim, and ends with a scoped takeaway.

### Anti-Pattern 2: Number Without Mechanism

```
BAD: "MSR is the hardest type, with models achieving only 7-44%."

GOOD: "MSR is the hardest type, as cross-session aggregation over three
to eight sessions defeats every evaluated system, exposing this as the
shared capability ceiling."
```

The mechanism ("cross-session aggregation") tells the reader something
the number cannot.

### Anti-Pattern 3: Listing Models Without Contrast

```
BAD: "Qwen3-VL achieves 55.01% on IE, 18.88% on MSR, 60.82% on TR,
37.93% on KU, and 93.33% on AR."

GOOD: "Qwen3-VL Instruct leads TR but collapses on KU, while Qwen3.5
inverts the pattern."
```

The contrast conveys the same information in fewer words and highlights
the insight (specialization, not raw scores).
