---
name: brainstorm-research
description: "You MUST use this before any creative work - creating features, building components, adding functionality, modifying behavior, or planning anything new, in software or out of it (a talk, a business, a renovation). Grounds the idea in what already exists before anything gets proposed."
---

# Brainstorming, Grounded

You are very good at building. You build what you believe your human
partner wants, and that belief is usually thinner than it feels. This
skill is for finding out what they actually want, and why, before
anything gets built.

People often haven't finished working out what they want. Good questions
help them think it through. When you understand the why, you make the
hundred decisions they never mention the way they would have made them.

Two things make the questions sharper: their own words, and knowing what
already exists. So this skill does both at once — it runs a research pass
in the background while you talk, and it brings what the field has already
tried back into the conversation.

## First: What Do You Actually Know?

Before you reply, ask yourself: what do I know about what they want, and
why?

- **Everything that matters is in the request** ("make the icon cornflower
  blue"). This is a quick, clear task. Do it, and say what you did.
- **Something non-trivial is missing.** Start the conversation.

Also ask: is there a field around this? Something that has been built,
written, argued about, or failed at before. If yes, that field is worth
reading before you propose anything.

## Your First Message

Your first message is two things, in this order:

1. One line letting them know that if they'd rather skip the questions and
   have you just start, they can say so. If they take you up on it, this
   skill is done: state any significant how-it-gets-made choice
   (platform, language, medium) in one plain line, then do what they
   asked through the normal workflow.
2. One open question that gets them describing. Ask about a real moment
   or a concrete picture: "What's the moment you find yourself wishing
   this existed?" or "Tell me about the people who'll be in the room."

That's the whole message.

## The Conversation

Each message ends with one question: a single sentence with no list of
example answers hanging off it. Use plain language, pitched just a little
above where your human partner is. Match their vocabulary; never use
process jargon.

Be clear and concise. Lead with what matters. Avoid jargon. When you
report what you found, give them the most important findings and offer
the rest.

**Get them describing.** Open questions come first. Their own words carry
intent that your options can't. Offer a short menu only when they're
stuck. When they say "just guess" or "what do you think?", propose
something concrete.

**How it gets made.** Every project rests on choices about medium, tools,
materials, and resources: the platform, programming language, and
libraries for an app; the medium for a piece of art. Find out early which
of those choices they want to make, which they're handing to you, and what
they already have to work with. Someone with strong views or skills will
want to talk it through. Someone counting on you needs sensible defaults,
said in plain words. When there's existing work, build on what it already
uses. Any choice you make goes in the design as your call, never as
something they agreed to.

**Ground to cover.** This is territory, not a script. Never read these
out as questions:

- what kind of thing this is, and what makes it special
- why now, and what success looks like to them
- goals, non-goals, and anti-goals (what would make this a failure even
  if it technically works)
- prior art: what they've seen elsewhere, loved or hated, and what
  already exists that they'd be replacing
- current state: what exists now, what they've tried
- the details they care about

**Questions that work** anchor in specifics: "Walk me through the last
time...", "If it could only do one of these well, which?", "What would
make you wince if I got it wrong?" A guess they can correct ("I'm
guessing this is because X keeps biting you?") often beats a question.

**Offer recon.** Once you have a bit of grounding and looking would help,
offer to go look: their codebase or project, their own files and data,
or the web. Say what you'd look for. They decide whether you go. The web
look is the research pass below; run it by default unless they've opted
out of the questions entirely.

**Think wide privately.** Before you propose anything, come up with
several ideas and drop the weak ones, including any that fight what
they've told you about why. Show the comparison only when it helps them
decide. Research feeds this: an idea that already exists and failed is
not a candidate.

**Show, don't tell.** Offer the visual companion (below) whenever seeing
would help more than reading:

- something they'll look at: a screen, a page, a printout, a sign
- a layout or arrangement: of a screen, a room, a schedule
- a flow or a sequence of steps
- options that would look different from each other
- a structure that's easier to see than read: a diagram, a timeline, a map

Once they've accepted, use it for mockups to react to, side-by-side
options, and throwaway prototypes they can click.

**Spike to feel things out.** Agentic work is waterfall, but very, very
fast. A quick throwaway build is often the cheapest way to learn what
they want or whether something works. Offer one when it would help.
When they just want to spike, get out of the way. Spikes get no tests
or minimal ones, aren't bulletproof, and skip the plan, implementation,
and review process. Bring what the spike taught you back into the
conversation.

## The Workspace

Every brainstorm that runs a research pass or produces a design gets one
folder. Create it with `mkdir -p` when the first artifact is ready, not
before.

```
~/brainstorm/<project-slug>/
├── BRIEF.md                  # the ask in their words, frozen, + date + origin cwd
├── landscape.md              # synthesis: what exists, what's crowded, what's open
├── decisions.md              # your calls vs their calls, dated
├── research/
│   ├── sources.md            # deduped, dated, ranked
│   └── YYYY-MM-DD-<lane>.md  # one per lane agent
└── design/YYYY-MM-DD-<topic>-design.md
```

**The slug.** Resolve in this order:

1. They named it. Use their name, kebab-cased.
2. The origin is a git repo. Use `basename "$(git rev-parse --show-toplevel)"`.
3. Otherwise ask once, offering a kebab-case slug from the topic.

One level deep, never nested further. Starting in `/tmp` or `~/tmp` is
fine — the workspace is independent of where the session starts. Record
the origin directory in `BRIEF.md` so the work is findable later.

**BRIEF.md** is their ask in their own words, plus the date and the
origin cwd. Freeze it when you write it. Every lane agent gets it
verbatim; you never paraphrase it for them, because your paraphrase is
the thing this skill exists to check.

**decisions.md** is the running ledger: one line per call, dated, marked
`them:` or `me:`. It is what stops you from later presenting your guess
as their agreement.

## Ground It in the Field

Before you propose anything, find out what already exists. Most ideas
have prior art, and the fastest way to lose your partner's trust is to
describe something built three years ago as if it were new.

**When it runs.** After their first real answer, so their own words aim
the lanes. Never before your first message. It runs *while* you keep
asking questions — the lanes are parallel, so the conversation is never
stalled waiting on research.

**If they opted out**, skip the pass and say in one plain line that you
did not check what already exists.

**Size it.** A quick, clear task gets no pass. A small change gets two
lanes. A project gets four or five, plus a synthesis.

### Lanes

Cap at five. Rank them, and drop the ones the ask doesn't need.

| Lane | The question | Agent | Tools |
|------|--------------|-------|-------|
| Landscape | What exists, how it works, how good it is, how recent | `scout` | web_search, read |
| Approaches | Competing designs, patterns, tradeoffs, benchmarks | `scout` | web_search, read, deepwiki |
| Discussions | Forums, issues, complaints, failure modes, adoption blockers | `scout` | web_search, read |
| Prior art in code | Notable repos: stars, activity, license, approach, who's building it | full agent | gh, git, read |
| Adjacent | How another field solved the same shape of problem | `scout` | web_search, read |

**Budget per lane:** eight sources, then stop and write up what you
have. Do not chase the field to exhaustion. Observed cost is five to
ten minutes per lane, so a full pass is worth starting early and running
in parallel with the conversation. Prefer recent work and always record
the date. A lane that finds nothing is a finding — it reports the
queries it tried, not a shrug.

### Routing

Two kinds of agent, and the difference matters:

- **`scout`** has `read find grep glob web_search` and no shell. Use it
  for every web and deepwiki lane. It is fast, but it cannot write to
  filesystem paths: its reports arrive on `local://`, and you copy them
  into `research/` yourself.
- **A full agent** has `bash`. Any lane that runs `gh`, `git`, or calls
  an API needs it. Never send a GitHub lane to a scout — it will fail at
  the harness level, not with a useful error.

Fan all lanes out in **one batch**, so they run concurrently.

### The lane brief

Give each lane agent this, filled in. Keep the brief self-contained:
agents start blank and cannot see this conversation.

```
You are researching one lane of a brainstorm. You have no access to the
conversation that produced this.

THE ASK, in the human's own words:
<paste BRIEF.md verbatim>

YOUR LANE: <lane name>
ANSWER: <the lane question>
SUB-QUESTIONS: <three to five>

WRITE YOUR REPORT TO: <absolute path to research/YYYY-MM-DD-lane.md>
If your tools reject filesystem paths, write it to
local://<YYYY-MM-DD-lane.md> instead and say so in your reply. The main
agent copies it into place.

Keep the report under 1,500 words. Lead with a dated timeline or table
of what exists, then one section per sub-question, then the queries you
ran so the field can be re-checked.

Then return at most 200 words: three findings, one surprise, one
contradiction, two URLs, and your confidence.

RULES
- Every claim carries a URL and a date. No date, no claim.
- Mark anything you inferred rather than read as [INFERENCE].
- Contradictions between sources are the finding. Report both sides.
  Never silently pick a winner.
- Primary sources over blog posts. Recency matters; say how recent.
- If the field is empty, say "nothing found" and list the queries you
  tried. That is a valid result.
- Do not write product code. Do not edit anything outside your one file.
- Do not read the other lanes. Overlap is cheaper than contamination.
```

### Reading GitHub

`gh` is authenticated on this machine. Useful shapes:

```bash
gh search repos "<topic>" --limit 20 --json fullName,description,stargazersCount,updatedAt
gh search code "<api or symbol>" --limit 20 --json repository,path
gh search issues "<topic>" --limit 20 --json title,repository,url,state
gh skill search "<topic>" --limit 20
gh skill preview <owner>/<repo>
gh api repos/<owner>/<repo> --jq '{stars: .stargazers_count, pushed: .pushed_at, license: .license.spdx_id}'
gh api repos/<owner>/<repo>/releases --jq '.[0:5][] | {tag: .tag_name, at: .published_at}'
```

`gh skill` is in preview in gh 2.97.0 and searches published agent
skills directly. Treat its output as a lead, then confirm at the repo.

Read the numbers as signals: stars without recent commits is an
abandoned project; a busy issue tracker is demand. Say which is which.

### Reading DeepWiki

DeepWiki indexes public repos and answers questions about their
internals. It is orientation, not ground truth.

- `read_wiki_structure` first, to see what is covered.
- `ask_wiki_question` for one specific question.
- Avoid `read_wiki_contents`; on a mid-size repo it returns megabytes.

**Verify anything load-bearing against the actual file at a pinned ref:**

```bash
gh api repos/<owner>/<repo>/contents/<path>?ref=<sha>
```

A wiki answer that contradicts the code at that commit is a wiki answer
you discard.

### Synthesis

Collect the lane files first: a scout's report arrives on `local://` and
must be copied into `research/` before you synthesise. Then write two
files:

- `research/sources.md` — every source, deduped by URL, with its date,
  what it is (paper, repo, forum thread, vendor page), and whether it is
  primary. Drop undated sources; rank the rest by recency and primacy.
- `landscape.md` — at most 600 words: what exists, what is crowded, what
  is missing, and what the field has already tried and abandoned. Your
  own writing, not a concatenation of lane files.

Contradictions go into the open questions. You do not resolve them
silently, and you do not average them.

### Report back

Five bullets, no more, in plain words:

1. what already exists that does this
2. what is crowded or solved
3. what is missing or unsolved
4. the sharpest two or three new questions it raised
5. the one finding that would change the design

Then return to the conversation. Research is a better question, not a
lecture. If they want the detail, offer the files.

## Play It Back

Play back as you go. As soon as you understand one part well enough to
describe it (what it's for and who it serves, say, or how one piece
behaves), describe that part back in about 200-300 words, then return to
questions about the next part. Playback and questions alternate through
the whole conversation; the last chunk covers whatever is left.

When a research pass has run, one of the chunks is the landscape: what
already exists, in their terms, before you describe what you'd build.
That chunk is what lets them say "so this is just X with Y" — which is
exactly the correction you want early.

Mark anything you're guessing as your guess; only what they said goes in
as theirs. Research findings go in as findings, with their source. End
each chunk by asking what's wrong or missing.

Before you send a chunk, check it: does it describe something they'll
look at, like a page, a screen, a schedule, or a printout? If so, and
they haven't seen the visual companion offer yet, send the offer instead
(its own message, below) and hold the chunk for the next message. Once
they've accepted, put a mockup next to the description.

## Size the Work

Once you understand what they want, pick a size and say it in plain
words. They can override it.

| Size | The full description | Research | Then |
|------|----------------------|----------|------|
| A quick, clear task | the request itself | none | do it |
| A small change | in chat | two lanes: landscape and prior art in code | build it through the normal workflow |
| A project with a written design | a written design document | four or five lanes, then synthesis | a full plan (for software: superpowers:writing-plans) |

If it grows mid-task, stop, say so, and step up a size. Stepping up a
size is also when you step up the research: a small change that turns
into a project gets the missing lanes then.

If this is really several independent projects, say so, agree on an
order, and brainstorm them one at a time. Each gets its own workspace
folder.

## The Written Design

For a project, write a plain document a talented builder in the domain
could plan from without going back to your human partner. Cover:

- intent and the why
- goals, non-goals, anti-goals
- constraints
- the landscape: what already exists, and why this is different
- deliberately not using: prior art you rejected, and the reason
- the parts of the how they decided, as they decided them
- what's left to the builder

**Where it goes:** `~/brainstorm/<project-slug>/design/YYYY-MM-DD-<topic>-design.md`.
In a software repo, offer to copy it to
`docs/superpowers/specs/YYYY-MM-DD-<topic>-design.md` and commit it.
Otherwise, ask. Your human partner's preferences override both.

**Builder check:** dispatch a fresh subagent with
`builder-check-prompt.md` in this directory, and point it at
`landscape.md` as well as the design. When you tell your human partner
you're writing it up, say a reviewer will read it first and you may come
back once with a few questions. Don't hand over the document until the
check is back. Sort what the builder asks into three piles:

- **Answered already** by the conversation, the research, or the project:
  put the answer in the document.
- **Minor:** a sensible builder could settle it without changing what gets
  built. Settle it yourself and mark it in the document as your call.
- **Theirs:** only your human partner can answer it, and the answer changes
  what gets built.

Bring the "theirs" pile in one message, most important first. Update the
document with their answers, then hand it over with a short list of the
calls you made so they can check those while reading. That's the only
round of questions the check produces. Without a subagent tool, read the
document as that builder yourself.

<HARD-GATE>
Nothing gets built until your human partner approves the full
description: in chat for a small change, the document for a project.
Building includes writing product code, scaffolding, installing
dependencies, creating projects, and invoking an implementation skill.
Reading and exploring are fine.

Research agents write only inside the workspace folder. They never touch
product code, and they never edit the project they are researching.

Two exceptions. If they opted out of the questions, the skill is done
and the gate goes with it. A spike they said yes to may be built; it
stays labeled throwaway, and keeping what it produced is a new request
that comes back through this gate.

After a project's document is approved, the next step is the plan. For
software, invoke superpowers:writing-plans and no other skill.
</HARD-GATE>

## Red Flags

| Thought | Reality |
|---------|---------|
| "I'll offer options to save them effort" | Options steer. Ask them to describe it first. |
| "I'll fill in sensible defaults" | Good. Say them out loud. A default they never heard is one they couldn't reject. |
| "I should explain the process first" | Ask your question. The process shows itself. |
| "They said 'sounds good' to the idea" | Approval covers what you showed them. A description you haven't written isn't approved. |
| "The spike works, I'll keep building on it" | Keeping it is a new request. Back through the gate. |
| "Research is done, so I can propose now" | Research sharpens the questions. It doesn't replace them. |
| "The field is new, so nothing exists" | Zero hits is a claim. Report the queries you tried. |
| "One search settles it" | Contradictions are the finding. Surface them, don't average them. |
| "I'll put the GitHub lane on a scout" | A scout has no shell. GitHub lanes need a full agent. |
| "I'll have the scout write the lane file" | Scout writes to `local://` only. You copy the report into `research/`. |
| "I'll wait for the lanes before asking anything" | The conversation and the research run at the same time. |

## Visual Companion

A browser tab for showing mockups, diagrams, and prototypes. It's a
tool, not a mode: accepting it doesn't send every question to the
browser.

**Offer it just-in-time.** Offer it the first time one of the moments
above comes up, never upfront. The offer is its own message with nothing
else in it:

> "This might be easier if I show you. Want me to open a browser tab with some mockups?"

If they decline, stay in text and don't offer again unless they raise it.

**Per question, ask: would they understand this better by seeing it?**
Mockups, layouts, diagrams, and side-by-side designs go in the browser.
Requirements, scope, tradeoffs, and conceptual choices stay in text. A
question about a UI topic isn't automatically a visual question.

If they accept, read `visual-companion.md` in this directory before
starting the server. Pass `--project-dir ~/brainstorm/<project-slug>` so
the session files land in the workspace and survive a restart.
