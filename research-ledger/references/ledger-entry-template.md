# Ledger entry template

Fill only the relevant fields; mark unknowns, never invent them. In a short conversation collapse into a few lines. In a permanent ledger add a new event and keep the old one.

## Event

- ID / date / script, environment, raw results:
- Kind: SIEVE (level 0, no ID) / PILOT / CONFIRMATORY / BLIND ROUND / REVIEW / REVISIT:
- Scope of judgement: literature up to date, terms, databases, nearest source; what was checked directly, what is reported:
- Origin (user's idea, paper, video, blind round, revisit) and artefacts checked directly:
- Original picture in the user's words (metaphor kept):
- Anchor: which measured or measurable system is the screen, and what would be measured on it:
- Genealogy (parent ID, related IDs, cluster on the map):
- Concrete claim / variant:
- Assumptions and domain of validity:
- Translation: objects, mechanism, what differs from the known, counterexample, forgery:
- Prior art (bridge or only pieces; sources with year):
- Epistemic label and reason:
- Preregistration: prediction, PASS, rejection, controls (+/−), forgery, power, threshold (and order of calculation), degrees of freedom, stopping rule, budget:
- User's bet before the run:
- Blind models' predictions before the run (who, what):
- Result with metric, uncertainty and link to raw results:
- Verdict (DEAD / LANDED / BRIDGE CANDIDATE / BRIDGE / EXPLANATION) + status (NOT TESTED / PILOT / PASS / FAIL / INVALID / RETRACTED / UNRESOLVED):
- Region of negligible effect and whether it was reached (FAIL ≠ absence of effect):
- Price (+C): the unwritten constant or assumption the idea paid:
- Blind round: models, convergence / complementarity / genre, who was right:
- Profile (if choosing): coherence; evidence; falsifiability; novelty; cost; leverage (each with a reason):
- Actual cost / estimate / budget:
- Conflict or change (corrects, supersedes, supports, contradicts):
- What the failure shows (which direction it closes, which it opens):
- What remains useful (new check, new method lesson, side result) + REGIME where the lesson holds:
- Revival conditions / possible recombinations (with which IDs):
- Decision: continue / narrow / fix / stop / UNRESOLVED:
- Next discriminating test and stopping rule:
- Git (full level): path of the entry, `PREREG <ID>` commit hash, results commit hash:
- Glossary: new terms from this event (standard term + reference, or "no standard term known"):

## Short form for a running log

`<ID> (<date>, <script>, pilot/confirmatory, preregistered; "<title in one sentence>") → <VERDICT> (<prior-art source>, scope: <up to date, terms>): <P1 … P3 holds/fails with numbers>; <what survives / what the failure shows>; lesson (regime: <…>): <new check, if any>`

## Illustrative cases

- A script prints "survives" because of a bug in the criterion, not in the physics: INVALID for the criterion; the physical conclusion is assessed separately; the fix is a new event.
- The prediction holds but the criterion formally fails at small N for lack of events: FAIL by the preregistration; a rerun with a 25× longer time is a new event. Lesson: test power is part of the preregistration.
- An algebraic proof under a fixed factorisation: PROVEN under the stated assumption; that the factorisation is the natural choice is a separate hypothesis.
- A phase effect disappears with log-normal strengths: not a hidden prohibition but an atom of a sum of equal contributions → DEAD as a new mechanism; LANDED on a known anti-concentration result (Littlewood–Offord) only once that was shown explicitly (an atom at zero, monotone decay with spread).
- A failed interpretation with a useful structure (H1 dead, H2 survives): keep the dead branch and its reason; a new descendant with its own prediction and test.
