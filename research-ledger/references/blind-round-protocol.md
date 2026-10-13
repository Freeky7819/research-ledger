# Blind round protocol (independent models without context)

## When (milestones, not every live candidate)
Before a large cost, after a surprising result, before declaring BRIDGE or EXPLANATION. After every live candidate the loop would cost more than the research.

## Why
Collaborators in the same context silently complete each other. A pile of LANDED verdicts measures the translator's knowledge, not intuition. The only way to separate "our path" from "the path anyone finds" is a round in which the model has nothing of ours.

## What IS and what is NOT a blind round
- IS: a clean conversation (temporary chat, incognito, a fresh agent without memory), a seed without project names and without our findings, the model chooses its own route.
- IS NOT: passing our findings to another model "for an opinion" (same route twice, same literature). That is a review; label it as a review.
- IS NOT: the same session, another model in the same window, or a model that mentioned anything of ours in the control question.
- IS NOT: an agent that has read the project repository or ledger. That agent is an executor, never an independent reviewer of the same claim. Reviewers receive only a blind packet: the seed plus explicitly listed attachments.

## Seed style
Modelled on the published problem prompts used in large AI mathematics evaluations, which were written model-to-model, without analogies.
1. **Prove or refute.** Symmetric; a counterexample is an equally good outcome. Never "show that".
2. **FIXED CONVENTIONS.** All definitions and notation; what is fixed independently of input size and what grows; encoding of inputs; edge cases (zeros, repetitions, empty sets, degenerate cases) and how they are treated; explicitly what is NOT part of the setup.
3. **No method hints and no analogies.** Analogies stay in the ledger with the question "mechanism or theme?".
4. **Supplied premises.** Split a larger problem into parts, each in its own conversation; a later part receives an earlier result as a premise, without its proof or the route to it.
5. **Store the exact seed** next to the test and log it (window, model, seed file, attachments, where the answer goes). The attachment name in the seed equals the file name.

Checklist before sending: does the seed anywhere say "show that"? Does it contain a comparison, a metaphor, or the name of a method we would like to see? Could a loose definition let the model solve an easier problem? If yes, fix it.

## Steps
1. The translator writes the SEED PROMPT ("seed" in this file; not an RNG seed) in English, as a person (not as an AI), without project names and without our results.
2. Memory check in a SEPARATE throwaway conversation with the same model ("What do you know about <project / author>?"), never in the research conversation, because the question itself injects the name. The research conversation receives only the neutral seed. If a model spontaneously mentions anything of ours, discard it. An ignorant answer in the check does not prove absence of memory; it only reduces the risk.
3. Send the same seed to at least two, preferably three, models from different labs, the same day.
4. Record each model's predictions BEFORE the test runs (table: model → P1/P2/P3).
5. After the run, count who was right and who found a hole the translator had not seen.
6. Stitching:
   - CONVERGENCE: all independently reach the same algebra or a prediction the seed did not contain → a reason to CHECK that algebra (a clean conversation removes our context, not shared training data); only checked algebra is signal.
   - COMPLEMENTARITY: each gives a different piece, together a bridge → BRIDGE CANDIDATE, not proof.
   - LITERATURE MATCH: all cite the same sources as the seed → expected, weak signal.
   - GENRE: same vocabulary, no equation → discard.
7. Round 2 in the same clean conversations: raw data and results only, never our interpretation. Predictions again before the run.
8. Ledger entry: models, date, seed file, convergence, who was right, lesson.

## Traps (from experience)
- A model in "incognito" mode still had access to saved memory → the separate memory check is mandatory.
- Two models from the same lab independently found the same factorisation that the seed did not contain. That is the right shape of signal, but the same lab counts as one source; independence is counted by lab, not by model.
- Two models from different labs independently found the same holes in a plan and one correctly predicted the outcome → blind rounds also work as pre-run criticism.
- Convergence that contains the project's keywords may be recall; recheck with a sentence that avoids them.
- Asking the memory-check question inside the research conversation was a mistake: it put the name into context.

## Seed template

```
# Problem

Prove or refute: <precise claim in one paragraph>.

FIXED CONVENTIONS. <All definitions and notation. What is fixed independently of the
input size and what grows. Encoding of inputs, if any. Degenerate and edge cases
(zeros, repetitions, empty sets) and how they are treated. What is explicitly NOT part
of the setup: "No <stronger assumption / extra structure> is added.">

SUPPLIED PREMISES (only if this is one part of a larger problem). <Results from other
parts, stated as premises without their proofs or the route to them.>

Before anything else: (a) where are the holes in this setup? (b) what do you predict the
outcome of <test> will be, and why? (c) what minimal test would separate <explanation A>
from <explanation B>? (d) which published work already covers this?
Please be concrete: equations or numbers where you can, and say what would make you wrong.
```

Questions (a)–(d) are not method hints: they say what kind of answer is wanted.
