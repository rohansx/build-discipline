# build-discipline

A single, language- and domain-agnostic engineering discipline you drop into your
AI coding flow (Claude Code, Cursor, or any agent that reads skills / rules files)
so it builds like a senior engineer instead of vibe-coding a demo that breaks on
contact with reality.

It's one file: [`SKILL.md`](./SKILL.md). That's the whole thing.

## What it's for

Models are good at producing plausible-looking code fast. What they skip by
default is the *discipline* that separates a demo from something that survives
real use: measuring the constants they'd otherwise guess, separating state so it
can't go stale, checking correctness with invariants instead of hope, and
assembling in gated stages. This skill externalizes that discipline into the
context so it happens by default.

It doesn't make a model "smarter." It makes the model *do the things a careful
engineer does* — which is a more honest and more useful claim.

## What's inside

Nine load-bearing principles, each earned from a real failure, each concrete
enough to apply to code you're writing right now — regardless of language
(Rust, TS, Python, Go…) or domain (services, parsers, pipelines, simulators,
tools, agents):

1. Separate source-of-truth / derived / ephemeral state — never persist what you
   can derive.
2. Keep a pure, seeded, reproducible core so you can actually test it.
3. **Calibrate every gating constant from printed data, never from intuition.**
   (The one that pays for the whole file.)
4. Prefer composable, data-driven rules over special-cases and global reads.
5. Assert invariants, not outputs — build the harness before the UI.
6. Isolate → stabilize → compose → tune → verify, gating every step.
7. Every automated judgment carries its reason; destruction needs a guard.
8. Coupled constants can be jointly impossible — check interacting ranges.
9. Design the degenerate case; make even the worst state coherent.

Plus a short section on applying it turn-by-turn inside an AI-assisted build loop.

## How to use it

**As a Claude Agent Skill:** install `SKILL.md` as a skill (or upload the packaged
`.skill` file) and it triggers automatically on real coding tasks.

**In any coding agent:** point your project rules at it — e.g. reference or paste
`SKILL.md` into `CLAUDE.md`, `.cursorrules`, or your agent's system context. It's
plain Markdown with nothing tool-specific.

**As a checklist for humans:** read it before starting a non-trivial build, and
keep the nine principles open while reviewing a PR.

## Provenance

Distilled from two real from-scratch builds — a self-improving knowledge system
and a multi-agent emergence simulator — that hit *the same underlying mistakes*
from opposite domains. The failure modes named in the skill (a threshold that
silently produced zero output, a drain/refill mismatch hidden behind healthy
averages, a pair of radii that made an interaction geometrically impossible) all
actually happened and were actually fixed. The specifics are the value.

## License

MIT.
