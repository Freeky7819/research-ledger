# Glossary entry template

One entry per term the project introduces. Purpose: a new name is not novelty. Before a term counts as new, check whether the same equation or concept already exists under a standard name.

```yaml
id: G-<slug>
term: "<our term>"
standard_term: "<standard mathematical / technical term>"   # or: "no standard term known"
reference: "<textbook, paper, or encyclopedia entry>"         # required unless no standard term
definition: "<one or two sentences, with the equation if there is one>"
first_used: "<ID or date>"
status: mapped | no-standard-term | provisional
notes: ""
```

Rules
- `mapped`: the term is a new name for a known thing. Use the standard term in anything that leaves the project.
- `no-standard-term`: after a recorded search (date, terms) no standard term was found. These entries are the map of genuinely new ground, and the first place a reviewer should look.
- `provisional`: not yet searched. A provisional term may not appear in a claim of novelty.
- Prefer adding an alias to an existing entry over creating a near-duplicate.
