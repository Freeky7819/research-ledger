# Preregistration template (freeze BEFORE the run; save as `<ID>_prereg.md`)

## Identity
- ID: canonical ID only from the canonical ledger owner; a parallel agent uses `X-<YYYYMMDD>-<slug>`
- Kind: PILOT (may search settings, never gives PASS) or CONFIRMATORY (frozen, new seeds/data)
- If confirmatory: link to the pilot and the list of ALL pilot variants tried (including failures)
- Date, author of the preregistration, script:
- Parent / related IDs (check the ledger that this is not a repeat):

## Hypothesis
- H (one sentence, no project names):
- What it buys if true (a prediction or prohibition that no known piece gives on its own):
- Prior art before the run: search scope (date, terms, databases), nearest source; why this is not already LANDED:
- Forgery (which fake world must fail, so that H is not a tautology):

## Predictions (each with a verdict HOLDS / FAILS)
- P1:
- P2:
- P3:
- Translator's sub-predictions (labelled with a name, counted separately):

## Criteria
- PASS: (number, threshold, direction)
- Rejection: (exactly what means DEAD, what means LANDED)
- Region of negligible effect: (below which effect size we say "practically no effect"; without it FAIL only means "did not reach PASS")
- Threshold matches the order of the calculation (leading order / numeric / exact):
- Threshold on the square of a quantity whose root is near zero:
- The threshold does not move after the result; a change = a new ID.

## Controls (run BEFORE the arms)
- Positive control (known case from the literature, must give the known number):
- Negative control (random / incoherent / gauge; must give zero or identical):
- "Must be identical" control (pure gauge, symmetry, relabelling):
- Heavy-tailed or unequal strengths: does the effect survive?
- Degrees-of-freedom count: parameters ≤ independent constraints for a unique fit, < for a testable prediction (neither sufficient; rank, symmetries, gauge subtracted):
- The control and the treatment must be algebraically distinguishable; write down why they cannot coincide by construction:
- Strongest simple baseline included, with equal accounting:
- Independent check (for a BRIDGE CANDIDATE): analytic step or second implementation, by whom:
- Does the setup reach the known maximum from the literature? (check before searching for deviations)

## Test power
- RNG seeds, number of events, sizes N (several scales, to separate a plateau from a trend):
- Noise estimate at the chosen size; the criterion requires effect > noise:
- Unit of analysis is the RNG seed; paired intervals; no pseudocounts at zero; UNDETERMINED is a valid outcome:

## Budget and stopping
- Time / model calls / money:
- Stopping rule (also on budget overrun: status INCOMPLETE, no guessing):

## Bets
- User's bet (also "don't know"):
- Blind models' bets (if a blind round with a seed prompt runs before the test):

## After the run (fill in only afterwards)
- Result, verdict (DEAD / LANDED / BRIDGE CANDIDATE / BRIDGE / EXPLANATION) + status, price (+C), what the failure shows, method lesson + the REGIME where it holds, next test:
