# Setup guide (first use, under five minutes)

Run this once per user or project when no `research-ledger.config.md` is found. Ask the questions in the user's language, a few at a time, offer the default in brackets, and accept "default" or "skip". Then write the config from `config-template.md`.

If an interactive question tool is available, use it for the multiple-choice questions.

## Questions

1. **Language and tone.** In which language should I answer? Do you want plain-language pictures of mechanisms alongside the formal part? [the language you write in; yes]

2. **Field.** What do you mostly work on? (e.g. theoretical physics, pure math, machine learning, biology, social science, mixed) This decides which checks are on by default. [mixed]

3. **Where the ledger lives.**
   - a) only in our conversation (I keep a running log you can copy),
   - b) a folder of Markdown files,
   - c) a Git repository (recommended for full strictness: preregistration commits are timestamped proof).
   Path or repository name, if b or c. [a]

4. **Who assigns canonical IDs?** One place must be the source of truth, so parallel sessions do not collide. Usually: your main conversation with me. ID prefix? [main thread; `L`]

5. **Models for blind rounds.** Which models from which labs can you open in a clean conversation (no memory, no project)? At least two labs are needed for a blind round to count. [none yet: blind rounds are skipped and verdicts stay at BRIDGE CANDIDATE at most]

6. **Roles.** Who plays Executor (code, long runs) and Critic (separate clean-context reviewer)? Any names you like for the roles? [Executor: a coding agent or me in a separate session; Critic: a separate session or another model]

7. **Strictness.** light / standard / full (see SKILL.md §0). [standard]

8. **Your own hypotheses.** Do you have a favourite theory or framework of your own? Name it, so I never use it as a premise and only bring it in at the end, carefully, if something survives. [none]

Optional, if the user wants: a glossary location, budget limits per test (time, model calls, money), and any standing lessons from earlier work they want added as checks (each with the regime where it was learned).

## After setup

- Write the config, show a three-line summary, and continue with the user's actual request.
- If the user later changes a setting, edit the config and log the change with a date.
- Never invent answers to setup questions; unknown stays at the default and is marked as default.
