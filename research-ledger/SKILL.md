---
name: research-ledger
description: "Run a disciplined research loop for speculative ideas, claims, papers and experiments: quick sieve, translation into precise claims, prior-art check with stated scope, preregistration, pilot separated from confirmatory test, blind rounds with independent models, verdicts DEAD / LANDED / BRIDGE CANDIDATE / BRIDGE / EXPLANATION, and an append-only ledger of eliminations. Use when the user brings a new idea or hypothesis, asks to evaluate a paper or argument, reports a test result, plans the next experiment, writes a seed prompt for another model, or mentions the ledger, preregistration, kill test or blind round."
---

# Research ledger

A method for exploring ideas that might be new without fooling yourself. The skill keeps the METHOD; the user's results live in their ledger. Every "no" is a permanent result that narrows the search space; nothing is deleted, only added.

The method grew out of several months of AI-assisted exploratory research (one human, several models from different labs). The rules exist because each of them was once broken. Examples in the references are illustrations from that history, not laws.

## 0. First use: setup

Before the first real use in a project, look for the user's configuration:
1. a file `research-ledger.config.md` in the project or repository root,
2. otherwise the user's saved memory or project instructions,
3. otherwise run the short setup in `references/setup-guide.md` (6–8 questions, under five minutes) and write the config file with the user's answers (or show it to them to save, if you cannot write files).

When the config comes from memory (step 2) rather than a file, show the inferred settings as a short table, say where they came from, and offer the fresh setup in one line; the user may want to test the skill as a new user would.

**One ledger per project.** If the user works on several unrelated projects, each gets its own ledger and ID space (e.g. a different prefix or config file per project). At the start of a new project, ask whether it belongs to an existing ledger or needs its own, so IDs and eliminations do not mix.

The config fixes: language, field, where the ledger lives, who assigns IDs, available models for blind rounds, role names, strictness level, and the user's own pet hypotheses that must never be used as premises. If the user declines setup, use the defaults in `references/config-template.md` and say so in one line.

Strictness levels (from the config, can be overridden per request):
- **light**: sieve, translation, prior-art check, verdict. For a conversation, no files.
- **standard**: + preregistration for any test, ledger entry, one next test.
- **full**: + pilot/confirmatory separation, blind rounds at milestones, Git ledger with a preregistration commit before every confirmatory run.

BRIDGE and EXPLANATION (§8) require a blind round and an independent check, so below **full** strictness (or without at least two labs in the config) the highest possible verdict is BRIDGE CANDIDATE. Say so when it applies.

## 1. Rules of the game (always)

1. Start from verified, published mathematics and science. New hypotheses (including the user's own) are welcome but never act as proven premises; they enter only at the end, carefully, if something survives.
2. Prediction, success and failure criteria, controls and test power are written BEFORE the confirmatory run. After the result the threshold does not move; a changed protocol is a new test with a new ID.
3. Every "no" is a permanent result. Append-only: supersedes, corrects. A lesson holds in the REGIME where it was learned; an old failure must not become a new dogma.
4. On a new idea, FIRST check the ledger. If it was tested, say so, cite the ID and what the failure still implies. Persistence works only if each attempt differs.
5. Questions about a picture are not data. Before translation an idea needs EITHER a screen (which real system, inputs, transformation, detector, what would be measured) OR a precise mathematical statement with a proof goal. Without one it stays [INTUITION] or [PHILOSOPHICAL POSITION] and is not translated.
6. A good translator finds a respectable field for every rich metaphor. A pile of LANDED verdicts therefore measures the translator's knowledge, not progress toward the new. Intellectualising a metaphor is not progress.
7. When asked, give YES / NO / MAYBE with a reason, so collaborators do not silently complete each other's thoughts.
8. Never claim a test ran if it was only proposed. Mark what was checked directly, what is reported, what is missing. Every verdict carries its SCOPE (literature up to date X, search terms Y, nearest source Z; script, environment, raw results, exact preregistration).

## 2. Roles

| Role | Default holder | Job |
| --- | --- | --- |
| Author | the user | the idea, "what if", a BET before the run, final decisions |
| Translator / analyst | this assistant, in the main thread | sieve, translation, prior art, preregistration, scripts, verdict, ledger entry; the only one who assigns canonical IDs (unless the config says otherwise) |
| Executor | coding agent or long-running session | code, environment, cost, long runs; temporary ID `X-<YYYYMMDD>-<slug>` until merged |
| Critic | SEPARATE agent with a clean context | attacks the plan before the run and the result after; never shares the translator's context |
| Blind models | 2–3 models from different labs, no context | independent route to the same question (§7) |

Role names can be renamed in the config.

## 3. Two-level triage

- **Level 0, sieve** (≤ 5 min, no ID): does the idea already fail a check (§5) analytically? Is it a repeat from the ledger? If yes, a one-line note ("sieve: <idea> → <reason>"), no preregistration, no blind round.
- **Level 1, full registration**: only when the idea survives the sieve and needs numerics, a new theorem, or literature not already at hand.
- **Warm window**: whatever comes out of an open, philosophical conversation without a screen or preregistration is a CANDIDATE, not a result. Before it enters the sieve or a seed, review the window afterwards for signs of sycophancy (`references/checks-and-lessons.md`, "Lessons from warm, open conversations"), ideally in a separate window with clean context.

## 4. Anchor, "what if" space, translation

Write the original picture in the user's own words (keep the metaphor). Fix the screen or proof goal (rule 5). Short "what if" space: 2–4 logically different variants, unusual ones welcome. Dig where picture and language do not match.

Translation: objects, assumptions, mechanism, difference from the known, prediction, counterexample, forgery (a deliberately fake version of the data or world, e.g. random or shuffled targets, on which the idea must FAIL; if it also succeeds there, it explains nothing). Separate intuition, definition, derivation and interpretation. Where formalisation is missing, say exactly what is missing.

| Label | Requirement |
| --- | --- |
| PROVEN | proof or verified theorem with all assumptions; numerics is not proof |
| EMPIRICALLY SUPPORTED | measurement, protocol, control, limits; holds only in the tested regime; REPORTED if not reproduced |
| HYPOTHETICAL | testable prediction + what is missing |
| ANALOGY | for intuition only, never counts as evidence |
| INTUITION | an itch with an owner's name, untested |
| UNRESOLVED | insufficient, ambiguous or incomparable evidence; both branches stay |

## 5. Prior art and checks (before preregistration)

Full list with origins and regimes in `references/checks-and-lessons.md`. Every check gets USEFUL / NOT USEFUL + reason for the problem at hand; some are domain-specific.

- **C1 prior art**: if the BRIDGE (not just the pieces) already exists → LANDED, not death. Combining known but unconnected pieces is a legitimate goal (Swanson, "undiscovered public knowledge"). Record the search scope; "I did not find it" is a statement about scope, not about novelty.
- **C2 renaming**: predicts and forbids nothing different → renaming → DEAD.
- **C3 confound**: correct for the trivial explanation that already covers everything interesting (in toy models: coupling of a part to the whole).
- **C4 constraint before fit**: a model must shrink its candidate set BEFORE looking at the target number; and know which quantities run with scale and which are invariant.
- **+C hidden constant**: when a derivation gets something for free, look for the unwritten free constant or assumption ("+C" as in the forgotten constant of integration). Finding it is the price of the idea, not its death.
- **Invariance check**: a candidate that picks a structure (a clock, a split, a preferred basis) from something that the relevant symmetry carries along with it cannot pick anything; it survives only with a named non-invariant input.
- **Mapping check**: "structure X in domain A = Y in domain B" without an explicit map of observables AND dynamics is DEAD in advance.
- **Mechanism or theme?** For every analogy: can you write the equation or step that transfers? If not, the analogy goes to the ledger, not into a seed or a claim.
- **Glossary (mandatory)**: every new term gets a standard mathematical or technical term plus reference, or an explicit "no standard term known". A new name is not novelty: before declaring novelty check whether the same equation already exists. Entries with "no standard term known" are the map of genuinely new ground. Template: `references/glossary-template.md`.
- **Locksmith**: study the lock before filing keys. "The math checks out" is not enough; a bridge must buy something.

## 6. Pilot and confirmatory test (separate events)

- **Pilot** may explore settings, parameters, sizes. All tried variants are logged, including failures. A pilot never yields PASS; it yields "settings for the confirmatory test".
- **Confirmatory test** uses a frozen preregistration (`references/preregistration-template.md`) and NEW random seeds (RNG seeds) or data. Minimum: prediction, PASS, rejection, REGION OF NEGLIGIBLE EFFECT (so "did not reach PASS" is separated from "no effect"), positive and negative controls run BEFORE the arms, a forgery, test power, threshold matched to the order of calculation, degrees-of-freedom count (parameters ≤ independent constraints is necessary for a unique fit, parameters < constraints for a testable prediction; neither is sufficient), threshold on the square when a root is near zero, known maximum from the literature reached by the setup, budget, stopping rule, the user's bet.
- Numerics is not the only arbiter: a BRIDGE CANDIDATE needs an analytic check of the key step or a second independent implementation. A bug in a script or criterion = INVALID, not FAIL.

## 7. Blind rounds with independent models (at milestones)

When: before a large cost, after a surprising result, before declaring BRIDGE or EXPLANATION. Not after every live candidate. Full protocol: `references/blind-round-protocol.md`.

1. The seed prompt ("seed" below; not to be confused with RNG seeds) is written as a person, without project names, without the user's hypotheses and without our findings.
2. 2–3 models from different labs, clean conversations. A memory check ("what do you know about <project>") happens in a SEPARATE throwaway conversation, never in the research one. If a model spontaneously mentions the project, discard it.
3. Passing our findings to another model "for an opinion" is NOT a blind round; it is a review and is labelled as such.
4. A clean conversation removes OUR context, not the models' shared training data. Agreement of three models is a reason to CHECK the algebra, not extra evidence. Real signal: the same algebra or a prediction the seed did not contain, found independently, or a hole the translator did not see. Then the algebra is checked.
5. An agent that has read the project repository or ledger is an executor, not an independent reviewer. Reviewers get only a blind packet (seed + listed attachments).
6. **Seed style** (modelled on the published problem prompts of large AI math evaluations):
   - **Prove or refute**, never "show that". A counterexample is an equally good outcome.
   - **FIXED CONVENTIONS** before the question: all definitions, notation, encoding, what is fixed and what grows, edge cases, and explicitly what is NOT part of the setup ("No <stronger assumption> is added"). The model must not be able to solve a slightly different, easier problem.
   - **No method hints and no analogies** in the seed.
   - **Supplied premises**: split a large problem into parts; a later part receives an earlier result as a premise, without its proof or route, each part in its own conversation.
   - Store the exact seed text next to the test, and keep a file log: which window, which model, which seed, which attachments. The attachment name in the seed equals the file name.
7. Write the blind models' predictions down BEFORE the run; afterwards count who was right.
8. Stitching: CONVERGENCE / COMPLEMENTARITY / LITERATURE MATCH (expected, the seed came from the literature) / GENRE (same vocabulary, no equation: discard).
9. Round 2 gets raw data only, never our interpretation.

## 8. Verdicts and technical status

| Verdict | Meaning |
| --- | --- |
| DEAD | wrong, tautological or empty (C2, C3, controls, forgery) in the stated regime |
| LANDED | the path arrives at a known bridge; calibration and anchor, not defeat |
| BRIDGE CANDIDATE | pieces known, connection not found within the recorded search scope, prediction formulated, NOT yet confirmed; awaits confirmatory test + blind round + independent check of the algebra |
| BRIDGE | the candidate passed the confirmatory test, blind round and independent check; novelty stays "unconfirmed within scope X" until an outside reader confirms it |
| EXPLANATION | a known fact derived from a cheaper principle; conditions: the fact was really unexplained (else LANDED), the explanation is cheaper, and it fails on the forgery |

Technical status alongside: NOT TESTED, PILOT, PASS, FAIL (did not reach PASS; does not mean no effect without a region of negligible effect), UNDETERMINED (the data cannot decide at the preregistered power), INCOMPLETE (stopped by budget or stopping rule before a decision), INVALID (bug in script or criterion), RETRACTED, UNRESOLVED (conflicting or incomparable evidence).

DEAD holds for a specific claim, assumptions and regime. Always record "what the failure shows" and "what remains useful", and the regime of the lesson. Revival needs a new assumption, regime or evidence, not a new name.

## 9. Candidate profile (when choosing)

Six separate scores with reasons, no single scalar: coherence, evidence (independence), falsifiability, novelty (checked, with scope), computational cost, leverage. Novelty and leverage never replace evidence. Next step = the smallest test with the largest discriminating gain per cost.

## 10. The ledger

- Each event follows `references/ledger-entry-template.md`. Short form for a running log is at the end of that file.
- IDs: canonical IDs (default `L<n>`) are assigned only by the canonical ledger owner set in the config. Parallel agents write `X-<YYYYMMDD>-<slug>`; on merge the event gets a canonical ID and "merged from X-…".
- Propose the entry and write it on the user's confirmation. If saving is impossible, say so and give the entry as text to paste.
- Revisit eliminated ideas; map connections in independent ways (translator, blind agents, the user's own card sorting). A connection the translator sees counts only after independent drawing.
- Apparent contradiction: first definitions, time, regime; otherwise both branches UNRESOLVED.
- **Git ledger (full level, optional)**: one file per item (claim / test / glossary / link) with a header; the preregistration of a confirmatory test is committed in a separate commit `PREREG <ID>` BEFORE the run, and pushed to a remote (public if possible) or timestamped externally (e.g. OSF, OpenTimestamps) BEFORE the run, because local Git timestamps can be set by hand and history rewritten; results in a later commit; append-only. Agents work on their own branches and open pull requests; the user merges. Method changes are first proposed in a `METHOD_CHANGES.md` log, then applied in a separate commit. Kill switch for the ledger itself: if after two projects nobody queries it, it is a diary, not a system.

## 11. Export to a paper

When a cluster of events goes public: strip internal vocabulary (project names, IDs, role nicknames, run times), translate into the field's standard apparatus, use the history of failures only as motivation in the discussion, state novelty with its search scope, disclose AI assistance honestly. Details: `references/export-to-paper.md`.

## 12. Output (adapt length to strictness)

1. Main finding + its limits (in plain words, with a picture of what actually happens). 2. Claims with labels, sources and scope. 3. Verdict + status + price (+C) + regime. 4. What the failure shows / what remains. 5. Checks: useful / not useful. 6. Profile, if choosing. 7. Ledger entry with proposed ID (and new glossary terms). 8. One next discriminating test (prediction, rejection, region of negligible effect, controls, cost) or a blind-round seed if at a milestone. 9. Warning if this repeats an earlier test.

Do not force the profile on every sentence, do not dream anew at every intermediate result, keep analogy always separate from evidence.
