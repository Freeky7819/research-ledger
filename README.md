# research-ledger

A skill for AI assistants (Claude, ChatGPT/Codex and others that read `SKILL.md`) that runs a **disciplined loop for speculative research**: you bring an idea, a paper or a test result, and the assistant helps you find out, cheaply and honestly, whether it is new, known, or dead, and keeps a ledger so you never test the same dead idea twice.

It is built for one person working with several AI models, where the main risk is not lack of ideas but **fooling yourself**: models agreeing with each other, metaphors dressed up as mechanisms, thresholds moved after the result, "not found in the literature" mistaken for "new".

## What it does

```
idea ──► sieve (5 min) ──► translation ──► prior art ──► preregistration
                                             │
                     LANDED ◄────────────────┤
                                             ▼
                       pilot ──► confirmatory test ──► blind round (milestones)
                                             │
                                             ▼
            DEAD · LANDED · BRIDGE CANDIDATE · BRIDGE · EXPLANATION ──► ledger
```

- **Sieve first.** Most ideas die in five minutes against a short list of checks. No paperwork for them.
- **Translation.** Every metaphor must become a measurable screen or a precise statement with a proof goal; analogies must pass "mechanism or theme?".
- **Prior art with scope.** "I did not find it" is recorded as a statement about the search (date, terms, nearest source), never as novelty.
- **Preregistration.** Predictions, thresholds, controls and power are frozen before the run. In a Git ledger, a separate `PREREG` commit pushed to a remote (or externally timestamped) before the run is the proof.
- **Blind rounds.** At milestones, the same seed goes to 2–3 models from different labs in clean conversations. Seeds follow a strict style: *prove or refute*, fixed conventions, no method hints, no analogies.
- **Five verdicts.** DEAD, LANDED (you rediscovered a known bridge — calibration, not defeat), BRIDGE CANDIDATE, BRIDGE, EXPLANATION.
- **Append-only ledger.** Every "no" is kept with what it shows and the regime where its lesson holds.
- **Glossary.** Every new term gets its standard name and reference, or an explicit "no standard term known". A new name is not novelty.

## Setup

On first use the skill asks 6–8 short questions (language, field, where the ledger lives, which models you can use for blind rounds, how strict to be, and your own favourite hypotheses so they are never used as premises) and writes `research-ledger.config.md`. You can skip it; defaults are sensible.

Where the settings come from, in order: a `research-ledger.config.md` file in the project, then what the assistant already knows about you (saved memory or project instructions), then the setup questions. If it uses memory, it shows you the inferred settings and offers the fresh setup.

**One ledger per project.** Unrelated projects should not share a ledger: give each its own config file or ID prefix, so eliminations and IDs do not mix. The assistant asks at the start of a new project.

Strictness: **light** (a conversation, no files), **standard** (preregistration and ledger entries), **full** (pilot/confirmatory separation, blind rounds, Git ledger). Without blind rounds the highest verdict is BRIDGE CANDIDATE.

## Install

The skill is the folder [`research-ledger/`](research-ledger/).

- **Claude Code**: copy the folder to `~/.claude/skills/research-ledger/` (all projects) or `.claude/skills/research-ledger/` in a repository.
  ```bash
  git clone https://github.com/Freeky7819/research-ledger
  cp -r research-ledger/research-ledger ~/.claude/skills/
  ```
  PowerShell:
  ```powershell
  git clone https://github.com/Freeky7819/research-ledger
  Copy-Item -Recurse research-ledger\research-ledger "$env:USERPROFILE\.claude\skills\"
  ```
- **Claude.ai**: zip the `research-ledger/` folder and upload it under Settings → Capabilities → Skills.
- **Codex / ChatGPT**: the folder includes `agents/openai.yaml`. For Codex, copy the folder to the skills directory your Codex version reads (commonly `~/.codex/skills/` or `.agents/skills/` in a repository; check your client's documentation). In ChatGPT, upload the zipped folder where your plan supports skills.

**Testing it as a new user.** If your assistant already knows you (memory, other research skills), it will adapt instead of asking. To see the onboarding a stranger gets, invoke the skill explicitly (`/research-ledger` in Claude) and say "run the fresh setup", or try it in a conversation without memory.

Then just talk: "here is an idea…", "evaluate this paper", "this test gave 0.62, what now?", "write a blind-round seed for this".

## Files

| File | What |
| --- | --- |
| `SKILL.md` | the method |
| `references/setup-guide.md` | first-use questions |
| `references/config-template.md` | config file and defaults |
| `references/checks-and-lessons.md` | checks and lessons, each with the regime where it was learned |
| `references/preregistration-template.md` | freeze before the run |
| `references/blind-round-protocol.md` | blind rounds and the seed style |
| `references/ledger-entry-template.md` | ledger entries, short form, illustrative cases |
| `references/glossary-template.md` | glossary entries |
| `references/export-to-paper.md` | turning a cluster into a paper |

## Honest limits

- The method reduces self-deception; it does not produce discoveries. Most ideas will end as DEAD or LANDED, and that is the method working.
- Blind rounds remove *your* context, not the models' shared training data. Agreement between models is a reason to check, not evidence.
- The checks come from a specific history (toy quantum models, combinatorics, small neural networks, numerology of constants). Each is labelled with its regime; rate it useful or not for your problem instead of applying it blindly.

## Origin

Developed in October 2026 by [Freeky7819](https://github.com/Freeky7819) over several months of exploratory research with several AI models (Claude, GPT, Gemini, Grok). The seed style was added after studying the published problem prompts in [openai/math](https://github.com/openai/math). Contributions and critiques are welcome: open an issue with the case where a rule failed you.

## License

MIT — see [LICENSE](LICENSE).
