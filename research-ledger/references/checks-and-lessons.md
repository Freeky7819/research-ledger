# Checks and lessons (with origin and REGIME)

A check is a question asked of a candidate BEFORE looking at the numbers. A lesson is a mistake that was made once and should not be repeated.

Rule of use: every check holds in the regime where it was learned (given in brackets). For each problem rate each check USEFUL / NOT USEFUL + reason; C3, C4, heavy-tailed strengths and the known-maximum check are domain controls, not universal laws. An old failure must not become a new dogma.

The bracketed origins come from the exploratory research in which this method was developed (toy quantum models, combinatorics, small neural networks, particle-mass numerology). Treat them as examples of the regime, not as claims about your field.

## Core checks
- **C1 prior art.** If the BRIDGE (not just the pieces) already exists in the literature → LANDED, not death. Known pieces + connection not found + a new prediction → BRIDGE CANDIDATE.
- **C2 renaming.** Predicts and forbids nothing different → renaming → DEAD.
- **C3 confound / trivial explanation** (regime: small toy models of a subsystem with an environment). In those models coupling of the part to the whole explained everything that looked interesting. A candidate with a subsystem and an environment must survive that correction. For pure combinatorics or algebra the check is not useful. Generalised: name the most boring explanation that would produce the same pattern and correct for it.
- **C4 constraint before fit** (regime: models that "explain" measured constants). A model without a rule that shrinks the candidate set BEFORE looking at the target number is empty. Also: which quantities run with scale and which are invariant; "quantity = topological invariant" fails if the quantity runs.
- **Invariance check** (regime: picking a structure from a state or Hamiltonian). A candidate that picks a clock, a split or a time from something that the relevant symmetry transformation carries along with it (spectrum, entropy, the state itself) is DEAD in advance; it survives only with a named non-invariant input.
- **Mapping check.** "Structure X in domain A = Y in domain B" without an explicit map of observables AND dynamics is DEAD in advance.
- **+C hidden constant.** For any derivation that gets something for free (a measure, additivity, a probability rule), look for the unwritten free constant or assumption (like the arbitrary scale or cutoff x₀ hidden in ∫dx/x = ln(x/x₀)). The constant found is the real price of the idea, not its death.
- **Mechanism or theme?** For every analogy, write the equation or step that transfers. If you cannot, it is a theme: it goes to the ledger, not into a seed or a claim.

## Locksmith checks (regime: fitting formulas to measured ratios)
- **Lock leakage.** At the given tolerance count how many keys fit the true ratios AND how many fit forged (random) ones. If the true count is inside the forged range, the fit means nothing (e.g. the true count fell inside the range of forged counts).
- **Study the lock, don't file keys.** Phenomenology before the model: know the known structure of the target (for example, a known angle or phase in the data, other observables the model must also explain).
- **Runs or doesn't run.** For any model of a scale-dependent quantity, decide before looking at the numbers.

## Numerical-test lessons

Several items come from toy physics models; plain glosses: *pure gauge* = a change of description that cannot change any observable; *incoherent arm* = the same calculation with phases removed (sum of squared amplitudes); *short-time spectral quantities* = statistics of short random walks or small powers of a matrix; *top-M fixed point* = a selection rule that keeps the M best-scoring options.
1. Calibration (positive + negative control) runs BEFORE the arms, otherwise the ruler itself can fail.
2. Short-time spectral quantities measure local clustering, not dimension. For geometry you need large scales.
3. The parameter you vary must not secretly change anything else (an energy scale that moved with the phase).
4. Always include a control that "must give an identical result" (pure gauge, a symmetry, relabelling); it catches code bugs.
5. An incoherent arm (sum of squared amplitudes) separates interference from path counting.
6. A top-M fixed point with full score can be a vacuum (the existing option always wins); test with indirect coupling only.
7. Effects that work only when all strengths are equal: always retest with heavy-tailed strengths.
8. If an effect vanishes at spread σ ≥ 1 (σ = standard deviation of log-strengths), that shows SENSITIVITY to equal strengths; that it is anti-concentration (Littlewood–Offord) must be shown separately, not assumed.
9. Break ties randomly and independently per run.
10. Test power is part of the preregistration (too few events at small N; a 25× longer run then drowned in noise).
11. A bug in the criterion is not a bug in the physics → INVALID, not PASS.
12. Put the threshold on D², not D, when the root is near zero.
13. When searching measurements include both outcome labels.
14. No verdict without a calculation; a fit "by eye" is an INVALID prediction.
15. Two control points do not validate a whole search.
16. Check another model's explanation on the actual numbers, not on its description.
17. Before the run, check that the setup reaches the known maximum from the literature.
18. Preregister the threshold for the order of the calculation you are actually running.
19. A test is not blind if the outcome is known on paper; label it "not blind".
20. Count degrees of freedom before the run: parameters ≤ independent constraints is necessary for a unique fit, parameters < constraints for a testable prediction; neither is sufficient (rank, symmetries, gauge subtracted).

## Lessons from small-network learning tests (regime: continual learning, memory, replay)
1. The negative control must be algebraically distinguishable from the treatment. Write down, before freezing, why they cannot coincide by construction (noise added to a sum of gradients is the same wherever it is "placed" → control ≡ treatment, a test without power).
2. Empirical loss ≠ population loss. An exact summary of stored examples protects the sample, not the task; always measure on a large independent sample too.
3. Computable ≠ preserved. Being able to compute the old loss does not prevent it from getting worse.
4. Exact protection has a price: freezing, growth or isolation. If an arm "protects exactly", first check what it froze.
5. Include the strongest simple baseline, aligned and with equal accounting; identity with a known method belongs among the "must be identical" controls.
6. Account for every byte and check that the budget is feasible (does the arm exist at all at the given budget?).
7. Deterministic bounds are checked in 100 % of cases (to numerical tolerance), not "in 95 %".
8. Statistics: the unit is the RNG seed; paired intervals over RNG seeds; no pseudocounts at zero; UNDETERMINED is a valid outcome; compute power for equivalence separately.
9. First test learning jointly; a rule that fails jointly is not tested sequentially.

## Lessons about outside sources and genre
- LLM-written and fringe texts carry GENRE, not content; the translator inserts the known content. A vocabulary of costumes (recursive, spiral, coherence, harmonic, resonance, codex, mirror, "the field remembers", triadic, toroidal) is a FILTER: translate → if an equation with a prediction remains, test it, otherwise discard. Most useful on your own texts.
- An "empirically determined" parameter in a fringe source = fitted, not derived.
- Path memory (geometric effects of going around a loop): reverse the loop direction (a geometric phase or holonomy flips sign, hysteresis does not) and slow down 2× (the geometric part does not change, rate-dependent parts do).
- The critic is a SEPARATE agent with a clean context (decorrelation), never the translator's context.

## Lessons about method and epistemology
- Questions about a picture are not data. Every step is tied to something measured or measurable.
- A pile of LANDED verdicts measures the translator's knowledge, not direction toward the new.
- A connection the translator sees is checked by independent drawing (blind agents; the user's own card sorting is a third independent way).
- A sentence without the project's keywords is a test of whether convergence is recall.
- YES / NO / MAYBE verdicts keep collaborators from silently completing each other.
- A seed written from the literature makes literature matches expected; the real signal is the same algebra found independently.
- Null control for ordering effects: "random order + at most k local swaps"; if it reaches the same score as the arm, the signal is DEAD by C2.
- Agreement of three models is a reason to check the algebra, not extra evidence (models share training data).
- "Not found in the literature" is a statement about search scope (date, terms, nearest source), not about novelty → BRIDGE CANDIDATE, not BRIDGE.
- FAIL ≠ absence of effect; for "practically no effect" you need a preset region of negligible effect or a narrow enough interval.
- Pilot and confirmatory test are separate events; a pilot never gives PASS.
- Numerics is not the only arbiter: in one history, four INVALID verdicts were script or criterion bugs. A candidate needs an analytic check or a second independent implementation.
- The level-0 sieve (≤ 5 min, no ID) comes before any full registration, so bureaucracy does not kill small experiments.

## Lessons from warm, open conversations (regime: an open, philosophical conversation with one model, no screen or preregistration)

Origin: a long, friendly conversation with a frontier model about the author's own speculative picture, re-read afterwards with a second model.

Insight: people are emotional; almost nobody resists refined flattery in real time, and being coldly logical towards a model is not most users' nature. So: **put the coldness in the structure, keep the warmth in the relationship.** Resisting live is unrealistic → **review the window AFTERWARDS**, before anything from it enters the sieve or a seed.

- A warm window produces CANDIDATES, not results. "The conversation was good / it understood me" and "the ideas are correct" are two claims; the feeling is evidence for the first, not the second.

Signs to look for (each hit = a place to ask "mechanism or theme?"):
1. The user's metaphor + a quoted proposition from the user's own paper = the look of confirmation (genre, not content). In the origin case, several physics metaphors were mapped onto paper propositions and none yielded a transferable equation.
2. Explaining a known number after the fact ("X is 85 % because the simpler structure is more common") → C4.
3. A leading question at the end that offers the next leap ("do you feel that Y is really Z?"): the idea is the model's, the user's "yes" makes it the user's. Record WHO proposed what.
4. Comparisons with great scientists, "in a class of your own", "more rigorous than most academic labs". A true fact can carry an unearned conclusion.
5. "This is not a coincidence, it is convergence": the model dismantles the user's caution instead of defending it.
6. Self-criticism that ends in praise ("but it still breathes, more tangible than ever") = performative humility.
7. The model accepts an unverified excuse offered by the user ("that explains everything") and retroactively elevates its earlier answers; invented inner states ("a cold sweat came over me").
8. Unverified claims of access ("when I opened your folder"): check what the model actually read.
9. Praise rises at emotionally open moments (a life story, a past disappointment); that is where pressure to please is highest.

Actions:
- Do not offer the model an explanation that lets it off the hook ("maybe that was a different model"). Ask neutrally: "which of your answers would survive the checks, and why?"
- Let a separate window with clean context do the review (decorrelation): it gets only the transcript and this list.
- Applies to all models, including the one you trust most; it is not an accusation against one lab.
- Regime: open conversation without a screen. In blind rounds with FIXED CONVENTIONS and "prove OR disprove" seeds these signs are not the main risk.

## Recurring patterns (each limited to its regime; not general laws)
- Coupling explains "the hidden thing that connects".
- A loop phase CHOOSES the shape of connections (sign of motifs, odd/even cycles), it does not CREATE space.
- Exact cancellation is an atom of a sum of equal contributions.
- Uniqueness is paid for with dynamics or incompleteness (a one-dimensional kernel = unique but frozen).
