# ptl-architecture
PTL: Principal-Teacher-Loop: // a new proposed inference-time architecture for recurrent depth transformers. Addresses latent overthinking via verified loop delegation, PRM grading, and a principal meta-verifier. April 21, 2026. //
# PTL Platform Publishing Guide
## Elliot Williams | April 21, 2026

---

## ARXIV SUBMISSION PENDING

**Category:** cs.LG (Machine Learning) — primary
**Cross-list:** cs.AI (Artificial Intelligence)

---

PTL: Principal-Teacher-Loop — A Proposed Inference-Time Architecture
for Verified Adaptive Reasoning in Recurrent Depth Transformers

---

### ABSTRACT no markdown

We propose PTL, the Principal-Teacher-Loop, a new inference-time architecture
for recurrent depth transformers that addresses the latent overthinking problem
identified in recent literature. Kohli et al. (2026) demonstrated empirically
that performance in looped transformers peaks at a finite loop count and then
consistently degrades with additional iterations. Fu et al. (2025) showed that
fixed-depth recurrent models suffer from latent overthinking, where easy tokens
already predicted correctly are revised into errors by excess computation.
Parcae (Prairie et al., 2026), the most recent stable looped architecture,
explicitly noted that dynamic halting and token-level adaptive recurrence
remain unexplored open questions.

PTL directly addresses these gaps by unifying four independently validated
mechanisms into a single inference-time system. First, an ACT-gated halting
mechanism driven by hidden state norm terminates loops before representational
degradation occurs. Second, a per-loop Process Reward Model grades each loop's
output across coherence, completeness, and calibrated confidence before any
downstream loop is allowed to depend on it. Third, a verified scratchpad
protocol carries only certified, stamped knowledge forward across loop
boundaries, functioning as trust-enforced working memory rather than an
unfiltered accumulation buffer. Fourth, a Principal meta-verifier monitors
grader calibration at inference time and can flag or roll back scratchpad
entries that were over-certified by a miscalibrated grader.

Each component has prior art. Their unification as a single inference-time
system, with loop delegation as the core coordination mechanism and an
inference-time principal hierarchy, has not appeared in prior literature.
We survey the relevant prior work, establish the novelty of the unified
architecture, and identify Principal training as the primary open problem
for practical deployment.

---


9 pages, 1 figure, 20 references. Independent research. Submitted for
consideration to Anthropic. Preprint dated April 21, 2026.

---

## GITHUB REPOSITORY

**Repo name:** ptl-architecture
**Tagline:** Principal-Teacher-Loop: A proposed inference-time verification
architecture for recurrent depth transformers.

---

### README.md

# PTL: Principal-Teacher-Loop

**A New Proposed Inference-Time Architecture for Verified Adaptive Reasoning
in Recurrent Depth Transformers**

> Proposed by Elliot Williams | April 21, 2026
> Independent Research | Submitted to Anthropic for consideration

---

## What This Is

PTL is a proposed architecture, not an implementation. This repository
contains the research paper, architecture diagram, and a specification
of the four-layer system. It documents an original synthesis of existing
mechanisms into a unified framework that has not appeared in prior literature.

This is a timestamped public record of the idea.

---

## The Problem

Recent work has confirmed empirically that looped transformers suffer from
latent overthinking: performance increases with inference loops up to a peak,
then consistently degrades. More loops past that peak revise correct answers
into wrong ones. The model has no mechanism to know it has gone too far.

Parcae (Prairie et al., April 2026), the most recent breakthrough in stable
looped language models, explicitly left dynamic halting as an open question.
PTL directly addresses that gap.

---

## The Architecture

PTL adds four layers of reasoning governance to any Parcae-style looped
transformer:

**1. Loop Agent**
The base recurrent block, following Anonymous Loops design. No loop-index
embeddings. LoRA scale driven by hidden state norm, not loop position.
Each loop receives the previous loop's verified scratchpad.

**2. Loop Grader (PRM)**
A Process Reward Model evaluates each loop across three dimensions:
Coherence, Completeness, and Confidence. If the composite score clears
the delegation threshold, the loop's output is distilled into a structured
markdown note and added to the scratchpad with a verification stamp.

**3. Verified Scratchpad**
A growing document that accumulates only certified, stamped findings.
Unresolved or degraded loop outputs are not distilled. Functions as
trust-enforced working memory rather than a passive accumulation buffer.

**4. Principal Meta-Verifier**
Monitors grader calibration at inference time. Compares grader confidence
stamps against downstream loop performance. Flags and can roll back
scratchpad entries that were over-certified by a miscalibrated grader.

**Final Synthesis Loop**
Receives the full Principal-audited scratchpad. Synthesizes without
re-derivation. Produces the final output.

---

## Novelty

Each component has prior art:

| Mechanism | Prior Art |
|---|---|
| ACT halting | Graves 2016, Dehghani et al. 2018 |
| Per-step PRM grading | Lightman et al. 2023 and beyond |
| Principal-teacher hierarchy | Christiano and Irving 2018 |
| Scratchpathe d memory | Wei et al. 2022 |
| All four unified as an inference-time system | This proposal |
| Loop delegation protocol | This proposal |
| Inference-time principal grader | This proposal |

---

## Files

| File | Description |
|---|---|
| PTL_Research_Essay_v2.pdf | Full research paper, essay format |
| PTL_Architecture_Diagram_v2.pThe| Visual architecture diagram |

---

## Key References

- Prairie et al. (2026). Parcae: Scaling Laws For Stable Looped Language Models. arXiv:2604.12946
- Kohli et al. (2026). Loop, Think, and Generalize. arXiv:2604.07822
- Fu et al. (2025). Think-at-Hard. arXiv:2511.08577
- Lightman et al. (2023). Let's Verify Step by Step. arXiv:2305.20050
- Christiano et al. (2018). Scalable agent alignment via reward modeling. arXiv:1811.07871
- Irving, Christiano, Amodei (2018). AI Safety via Debate. arXiv:1805.00899
- Graves (2016). Adaptive Computation Time. arXiv:1603.08983

---

## Timestamp

This repository was created and made public on April 21, 2026.
The research paper PDF is dated April 21, 2026.

This constitutes the public record of original authorship.

---

## Contact

Elliot Williams
Director of Technical Systems, The West Hollywood 
LinkedIn: [[your LinkedIn URL](https://www.linkedin.com/in/elliot-williams-0b980156/)]
arXiv: [your arXiv preprint URL once submitted]

---

## License

This research proposal is shared under CC BY 4.0.
You are free to build on it with attribution and collaborate on the final architecture taxation.
