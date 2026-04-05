---
name: anti-hype-prose
description: >-
  Keeps technical writing opinionated, factual, and practical—no marketing tone,
  hype, or vague uplift. Use when drafting or editing READMEs, docs, ADRs,
  changelogs, release notes, PR descriptions, comments, blog or MDX content, or
  when the user asks to avoid "marketing slop," grandiosity, LinkedIn voice, or
  overclaiming impact.
---

# Anti-hype technical prose

## Goal

Voice should read like someone explaining a model to peers: specific claims, evidence, tradeoffs. Audience may be contributors, users, or reviewers—**sales language is not** appropriate for any of them. Strong opinions are welcome when they are grounded.

## Red flags (cut or rewrite)

- **Life/work transformation**: "changed how I work," "game-changer," "day-to-day work," "everything clicked," "I never looked back."
- **Vague uplift**: "more confidence," "faster," "easier," "better DX" **without** what was slow/hard before and what changed (one concrete scenario beats three abstractions).
- **Universal claims without proof**: "everyone," "most teams," "the industry," "production-ready"—unless you cite a source or narrow to "in my experience" / "on teams I've seen" / "in this repo."
- **Slogans and taglines**: "Make the invisible visible," "X is not a nice-to-have, it's table stakes," "the future of Y."
- **Stacked superlatives**: revolutionary, incredible, seamless, magical, world-class, enterprise-grade (unless you define what that means here).
- **Motivational filler**: "Here's the thing," "At the end of the day," "It all boils down to."

## Preferred moves

- **Ground the I or we**: "We spent less time inferring X" instead of "It transformed our workflow."
- **One falsifiable sentence**: what you could observe or measure (even qualitatively: "I could see serialized payload in DevTools").
- **Admit limits**: what the tool or design still does _not_ do; where the mental model or API still breaks.
- **Opinion as hypothesis**: "I suspect…" / "My read is…" when you lack data.
- **Earned emphasis**: short sentences after long explanation; avoid bold claims in the opening line of a paragraph.
- **Changelogs and release notes**: prefer **what changed** and **how to migrate** over adjectives; link issues/PRs when useful.

## Quick pass before done

1. Search for: `changed`, `transform`, `confidence`, `game`, `revolution`, `seamless`, `invisible`, `visible`, `everyone`, `never`, `always` (not all bad—re-read in context).
2. Replace testimonial openers ("That changed… for me") with **observed effect** ("I could correlate UI with server routes in one panel").
3. Replace slogans with **one concrete behavior** the reader could replicate or verify.

## Fit the project

If the repository defines tone or content rules (e.g. `AGENTS.md`, `CONTRIBUTING.md`, `docs/` style notes, or a content/voice guide), follow those **after** applying this skill—they may add constraints (inclusive language, terminology, audience level).
