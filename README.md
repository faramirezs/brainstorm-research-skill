# brainstorm-research

An agent skill that grounds creative work in **what already exists** before anything gets proposed.

It does two things at once: it interviews you with one open question at a time, and it runs a
research pass in the background so that the ideas you end up considering are not things that were
built and abandoned three years ago.

## When it fires

> You MUST use this before any creative work — creating features, building components, adding
> functionality, modifying behavior, or planning anything new, in software or out of it (a talk, a
> business, a renovation). Grounds the idea in what already exists before anything gets proposed.

It is not a planning skill and not an implementation skill. It runs *before* those, and it ends by
handing them a document they can work from.

## What it does

- **Opens with one question.** The first message offers an opt-out in one line, then asks one open
  question that gets you describing — never a menu of options, which would steer you.
- **Researches the field while you talk.** Up to five lanes (`scout` agents for web and DeepWiki,
  full agents for anything needing `gh` or `git`) fan out in one batch after your first real answer.
  The conversation never stalls waiting on research.
- **Plays understanding back in chunks.** Every 200–300 words of description, it hands the
  understanding back for correction. When research has run, one of those chunks is the landscape —
  what already exists, in your terms — which is what lets you say *"so this is just X with Y"* early.
- **Sizes the work and says so.** A quick task, a small change, or a project with a written design.
  You can override the size. Growing mid-task means stepping up a size and stepping up the research.
- **Writes a design a builder can plan from.** Intent, goals, non-goals, anti-goals, constraints, the
  landscape, prior art deliberately rejected, the calls you made, and what is left to the builder.
- **Gates the build.** Nothing gets built — no product code, no scaffolding, no dependency installs —
  until you approve the full description.
- **Shows instead of telling, when seeing is easier.** An optional browser tab for mockups, layouts,
  diagrams, and side-by-side options. It is offered just-in-time, never upfront.

## Install

```bash
npx skills add faramirezs/brainstorm-research-skill
```

Or copy the directory into your agent's skills folder:

```bash
git clone git@github.com:faramirezs/brainstorm-research-skill.git \
  ~/.agents/skills/brainstorm-research
```

## What it leaves behind

Every brainstorm that runs a research pass or produces a design gets one workspace folder,
`~/brainstorm/<project-slug>/`, one level deep:

```
~/brainstorm/<project-slug>/
├── BRIEF.md                  # the ask in your words, frozen, + date + origin cwd
├── landscape.md              # synthesis: what exists, what's crowded, what's open
├── decisions.md              # the agent's calls vs yours, dated
├── research/
│   ├── sources.md            # deduped, dated, ranked
│   └── YYYY-MM-DD-<lane>.md  # one per lane agent
└── design/YYYY-MM-DD-<topic>-design.md
```

`BRIEF.md` is frozen and handed to every lane agent verbatim, so no paraphrase of your ask can drift.
`decisions.md` marks each call `them:` or `me:`, which is what stops a guess from later being
presented as your agreement.

## Files

| File | Purpose |
|---|---|
| `SKILL.md` | The skill itself: the conversation, the lanes, the synthesis, the size gate, the design |
| `visual-companion.md` | The optional browser tab for mockups — offered just-in-time |
| `builder-check-prompt.md` | The prompt for the reviewer that reads the design before you do |
| `scripts/` | The visual companion server (Node.js built-ins only, no dependencies) |

## Requirements

Any agent that can read `SKILL.md` and spawn subagents. The visual companion needs Node.js; it uses
no npm packages. The research lanes assume `gh` is authenticated if a GitHub lane is used.

## License

MIT — see [LICENSE](LICENSE).
