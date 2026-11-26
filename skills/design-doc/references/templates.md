# Templates

Plain templates, used when the user gives none and the project has no
documents of that type to follow. Drop a section that would be empty, except
the ones marked required. Every type starts with the same header and ends
with the same change log.

## Header (all types)

```markdown
# <Title>

- Type: ADR | RFC | Design doc | Storyline
- Status: draft | in review | accepted | rejected | superseded
- Date: <YYYY-MM-DD> | Revision: <n>
- Author: <the user>
- Readers: <who should read it, and what they are asked to do>
```

## Change log (all types, from revision 2)

```markdown
## Change log

### Revision 2, <YYYY-MM-DD>
- <what changed> (<the comment or request that caused it>)
- Declined: <comment>, because <reason>
```

## ADR

One page. The title is the decision, stated as a sentence: "Store sessions in
Postgres instead of Redis".

```markdown
## Context
<The situation and the forces at play: what makes a decision necessary now.
Facts, with how you know them.>

## Options
1. <option>: <what it gives, what it costs>
2. <option>: <what it gives, what it costs>

## Decision
<The option chosen and the reason, in the user's terms. Required.>

## Consequences
<What becomes easier, what becomes harder, what has to be done because of
this, and what would make us revisit it.>

Assumptions: <what was filled in and not confirmed, or "none">
Open questions: <what is still unanswered and who can answer, or "none">
```

## RFC

A proposal that wants to be challenged. The reader should reach the open
questions within the first screen.

```markdown
## Summary
<Three or four sentences: the problem, the proposal, what you want from the
readers and by when.>

## Open questions for reviewers
- **Open:** <question> (<who can answer>; <what the answer changes>)

## Motivation
<Why this, why now, what happens if nothing is done.>

## Goals, non-goals, anti-goals
- Goal: <...>
- Non-goal: <out of scope on purpose>
- Anti-goal: <what would make this a failure even if it works>

## Proposal
<What is proposed, concrete enough to picture. Label each statement a
reviewer could challenge.>
- **Decided:** <...> (<reason given>)
- **Assumed:** <...> (<reason>)

## Alternatives considered
<The two or three real ones: what each trades off and why it was not picked.
Required.>

## Risks and what is not known
<What could go wrong, how it would show, what is still unmeasured.>
```

## Design doc

How something will work. Long enough that a capable builder in the field
could work from it without coming back to the author, and no longer.

```markdown
## Summary
<What this is and why it exists, in a short paragraph.>

## Context
<How things work today and what this touches, with pointers (files, links).>

## Goals, non-goals, anti-goals

## Constraints
<What cannot change: versions, budgets, deadlines, compatibility, rules.>

## Approaches
<The two or three ways considered, what each trades off, which was chosen and
why. Required.>

## Design
<The chosen approach in detail: parts and their responsibilities, the
interfaces between them, data, flows, failure behaviour. A diagram or a
sketch in text where seeing helps more than reading. Label each statement a
reviewer could challenge.>

## Left to the builder
<Choices deliberately not made here.>

## Open questions
- **Open:** <question> (<who can answer>; <what the answer changes>)
```

## Storyline

For a talk or a presentation. It fixes what the audience should leave with and
the order of the argument. It stops there: no slides, no visual design, no
speaker notes.

```markdown
## Audience
<Who is in the room, what they already know, what they care about, what they
are sceptical of.>

## Takeaway
<The one sentence they should be able to repeat a week later. Required.>

## Setting
<Length, format, what comes before and after, what the audience is expected
to do afterwards.>

## Beats
1. **<the claim of this beat, as a sentence>**
   Support: <the example, number, demo or story that carries it>
   Leads to the next because: <the link>
2. ...

## Opening and close
<How it starts (the hook, in one or two lines) and how it ends (the last
thing said, and the ask if there is one).>

## Left out on purpose
<What a knowledgeable listener will expect and not get, and why.>

## Open questions
- **Open:** <question> (<who can answer>; <what the answer changes>)
```

A beat is one claim. If a beat needs "and", it is two beats. Label a beat
`Assumed` when the claim or its support is yours and not the user's.
