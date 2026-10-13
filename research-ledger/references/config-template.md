# research-ledger.config.md (template)

Save as `research-ledger.config.md` in the project or repository root. Lines starting with `#` are comments. Values left at default are marked `(default)`.

```yaml
version: 1
updated: YYYY-MM-DD

language: en                     # answer language
plain_pictures: true             # add a plain-language picture of each mechanism
field: mixed                     # physics | math | ml | bio | social | mixed

strictness: standard             # light | standard | full

ledger:
  location: conversation         # conversation | folder | git
  path: ""                       # folder path or owner/repo
  id_prefix: "L"                 # canonical IDs: L1, L2, ...
  canonical_owner: "main thread" # the only place that assigns canonical IDs
  parallel_id: "X-<YYYYMMDD>-<slug>"
  glossary: "with the ledger"     # where glossary entries live (same place as the ledger, a folder, or a single file)

roles:
  author: "user"
  translator: "assistant (main thread)"
  executor: "coding agent / separate session"
  critic: "separate clean-context session"

blind_round:
  labs:                          # at least two labs for a round to count as independent
    - lab: ""
      models: []
  memory_check: "separate throwaway conversation"

pet_hypotheses:                  # never used as premises; only at the end, carefully
  - ""

budget:
  per_test: ""                   # time / model calls / money
  stop_rule: "on budget: status INCOMPLETE, no guessing"

standing_lessons:                # optional; each with the regime where it was learned
  - lesson: ""
    regime: ""
    source: ""
```

## Defaults when the user skips setup

language = the user's language; plain_pictures = true; field = mixed; strictness = standard; ledger in conversation, prefix `L`; no blind-round labs (blind rounds skipped, so no verdict above BRIDGE CANDIDATE); no pet hypotheses.
