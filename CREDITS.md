# Credits

`brainstorm-research` is a derivative of the `brainstorming` skill by **Jesse Vincent**
([@obra](https://github.com/obra)), from the [Superpowers](https://github.com/obra/superpowers)
collection.

| Skill | Author | Organisation | URL |
|---|---|---|---|
| `brainstorming` | Jesse Vincent | Superpowers | <https://github.com/obra/superpowers/blob/main/skills/brainstorming/SKILL.md> |

Upstream revision this skill was derived from: `2ce8aa1` (Superpowers v7.0.1, 2026-10-21).

## What came from upstream

- **`SKILL.md`** — the conversation structure, the first-message and opt-out rules, the questions,
  playback, sizing, the written design, the hard gate, the Red Flags table, and the visual companion
  offer are upstream work, edited here. Roughly half the body lines are unchanged; the rest is
  rewritten to add the research pass, the workspace, the lanes, and the synthesis.
- **`visual-companion.md`** — copied verbatim.
- **`builder-check-prompt.md`** — copied verbatim.
- **`scripts/`** (`server.cjs`, `start-server.sh`, `stop-server.sh`, `helper.js`,
  `frame-template.html`) — copied verbatim.

Verbatim files are left byte-identical to upstream, so `diff` against
`https://github.com/obra/superpowers/tree/main/skills/brainstorming` still verifies which content is
upstream and which is this skill's. Attribution for those files lives here, and in the
`metadata.credits` block of `SKILL.md`.

## What is original to this skill

The research pass: the workspace layout (`~/brainstorm/<project-slug>/`), the lane brief and
routing rules, the web/DeepWiki/GitHub lanes, the landscape synthesis, `BRIEF.md`/`decisions.md`,
and how research feeds the playback and the design.

## Upstream licence

MIT. Reproduced as required by its terms:

```text
MIT License

Copyright (c) 2025 Jesse Vincent

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```