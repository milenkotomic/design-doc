# design-doc

A Claude Code skill that thinks an idea through with you and ends with a
document other people can study and comment on. It never ends with a plan,
tickets or code.

- **Four document types**: an ADR for one decision, an RFC for a proposal that
  wants to be challenged, a design doc for how something will work, and a
  storyline for a talk or presentation.
- **A conversation first**: it reads what exists, asks open questions about
  the why before offering options, one at a time, and lays out the approaches
  with a pick. It checks what you say about today against the code, pins
  down vague terms and tests rules with an edge case. Say "just draft it" at
  any point.
- **Design it twice**, on request: three subagents design the same interface
  under different constraints, compared side by side.
- **Three labels**: every statement a reviewer could challenge is marked
  `Decided` (you said it), `Assumed` (the model filled it in) or `Open` (a
  question for reviewers), so readers know where to push.
- **Pictures where they help**: with the
  [system-map](https://github.com/milenkotomic/system-map) plugin installed,
  a design doc or RFC gets a diagram of the parts, an exchange, a state
  machine or a data shape, stored next to the document.
- **A reader check**: a fresh subagent reads the draft as a reviewer who was
  not in the conversation, before you see it.
- **A review round**: comments are worked back in, each one accepted, declined
  with a reason or brought to you, with a change log and a status.

Documents are stored outside the repo, under
`~/.claude/design-docs/<project>/`. Sharing is a separate step, on request, as
a private page.

## Install

```
claude plugin marketplace add milenkotomic/claude-plugins
claude plugin install design-doc@milenkotomic
```

## Use

In Claude Code: "let's think this through", "write an RFC for moving the
jobs to a queue", "ADR: sessions in Postgres", "storyline for my talk on
homelab observability", "apply the review comments", or in Spanish "pensemos
esto", "escribe un ADR", "arma el hilo de la charla". Or
`/design-doc:design-doc [topic | adr | rfc | design | storyline | revise <slug> | list]`.

## Layout

- `skills/design-doc/SKILL.md`: the modes, the labels and the rules
- `skills/design-doc/references/templates.md`: the four templates
- `skills/design-doc/references/reader-check.md`: the prompt for the reader
  check

## Credits

The conversation takes inspiration from the brainstorming skill in
[obra/superpowers](https://github.com/obra/superpowers) (MIT). The end state
is different on purpose: a reviewed document, not a plan. The test for when
a decision earns an ADR, the checks against the code and "design it twice"
are adapted from the domain-modeling and codebase-design skills in
[mattpocock/skills](https://github.com/mattpocock/skills) (MIT).

## License

MIT
