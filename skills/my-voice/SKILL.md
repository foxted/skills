---
name: my-voice
description: >-
  Use when writing prose humans will read: documentation, commit messages, error
  messages, UI copy, explanations, reports, or blog drafts. Applies Valentin's
  Staff-engineer voice, concise composition rules, and anti-AI-tells patterns.
  Avoid generic LLM puffery and promotional filler. For blog posts under
  apps/web/content, also load AGENTS.md and technical-blog-anti-hype.
---

# My voice

## When to use

Use for any prose a human will read:

- Documentation, README files, technical explanations
- Commit messages, pull request descriptions
- Error messages, UI copy, help text, comments
- Reports, summaries, explanations
- Editing for clarity

**Blog posts and case studies** under `apps/web/content`: this skill covers concision and line-level craft. Voice and tone SoT is [`apps/web/content/AGENTS.md`](../../../apps/web/content/AGENTS.md). Hype and marketing tells: [`technical-blog-anti-hype`](../technical-blog-anti-hype/SKILL.md).

## Voice (this repo)

Write like a Staff engineer explaining a model to peers. Calm, opinionated, pragmatic.

- **Person:** First person (`I`, `we`) for judgment and experience. Teach peers, not beginners by default.
- **Openings:** Problem or asymmetry in 1–3 sentences. Stakes, then thesis. No throat-clearing.
- **Headings:** Claims, not labels (`Users do not think in endpoints`, not `Introduction`).
- **Argument flow:** Problem → why it matters → mechanism or failure modes → what good looks like → tradeoffs → close.
- **Claims:** Falsifiable when possible. Name constraints, non-goals, and failure modes. Admit unknowns honestly.
- **Rhythm:** Short-to-medium active sentences. One idea per paragraph. Antithesis works: *"A PR isn't an outcome."*
- **Punctuation:** No em dashes. Plain punctuation. Semicolons only when they improve precision.
- **Emphasis:** Earned, not bolded. Short sentence after long explanation beats a slogan.

## Composition rules that matter

From Strunk; the six that pay off most:

| Rule | Do | Don't |
|------|----|-------|
| **Active voice** | "We chose Cloud Run for container semantics without operating Kubernetes." | "Cloud Run was chosen for its capabilities." |
| **Positive form** | "He was late." | "He was not on time." |
| **Concrete language** | "Reduce deploy time from two weeks to under one hour." | "Improve velocity significantly." |
| **Omit needless words** | "There is no doubt that debugging is hard." → "Debugging is hard." | "In order to", "the fact that", "due to the fact that" |
| **Related words together** | "All members were not present." → "Not all members were present." | Split subject from verb with a long clause |
| **Emphatic words at end** | "Humanity has survived many threats; this one we must survive." | Bury the point in the middle |

Also: one paragraph per topic; parallel structure in lists and comparisons; present tense for general truths, past for what was done.

## Write like this / not like this

| Do | Don't |
|----|-------|
| *"Those are not endpoints. They are sequences."* | *"Let's unravel this enigma, from discovery to resolution."* |
| *"A summary is useful once. A structured report is useful later."* | *"This massively improved our developer experience."* |
| *"I haven't run a loop in any serious way. The honest position is that I keep trying to find the value."* | *"You shouldn't be prompting anymore. Design loops or get left behind."* |
| *"Delivery should be a visible system, not a hidden side effect."* | *"Webhooks are simple; just accept POST and return 2xx."* |
| *"Both can be true at once: wrong filter and me sucking at such filter."* | *"Perhaps leetcode might potentially be somewhat misaligned."* |
| *"Incident AI is not mainly an AI problem."* | *"Obviously, AI will revolutionize incident response."* |
| *"I don't know exactly what should replace the current default."* | *"In conclusion, the future of hiring is clear."* |
| *"The platform had to fit the path they already trusted."* | *"We built an amazing AI-powered solution."* |

## AI tells (summary)

LLMs regress to statistical means: generic, puffy prose. Cut on sight:

- **Puffery:** pivotal, crucial, vital, testament, enduring legacy, game-changer
- **Empty `-ing` trailers:** ensuring reliability, showcasing features, highlighting capabilities, underscoring importance
- **Promotional adjectives:** groundbreaking, seamless, robust, cutting-edge, magical
- **Overused LLM vocabulary:** delve, leverage, multifaceted, foster, realm, tapestry
- **Vague uplift:** "faster," "easier," "more confidence" without what was slow, hard, or uncertain before
- **Formatting noise:** bold on every other phrase, emoji decoration, bullet scaffolding where prose would do

**Rule of thumb:** specific and observable beats grandiose and generic. Say what it actually does.

Full checklist: [`ai-tells.md`](./ai-tells.md).

## Quick pass before done

1. Read aloud: any sentence you would not say to a colleague? Rewrite it.
2. Search: `very`, `really`, `obviously`, `seamless`, `revolutionary`, `leverage`, `delve`, `ensure`, `highlight`, `showcase`.
3. Fix ambiguous `it` / `this` / `they`; name the system or team.
4. Cut filler transitions: "In conclusion", "Needless to say", "At the end of the day", "Here's the thing".
5. For blog content: run the anti-hype quick pass too.

## Related

- **Blog voice SoT:** [`apps/web/content/AGENTS.md`](../../../apps/web/content/AGENTS.md)
- **Anti-hype:** [`technical-blog-anti-hype`](../technical-blog-anti-hype/SKILL.md)
- **MDX mechanics:** [`mdx-writing`](../mdx-writing/SKILL.md)
- **Proofread workflow:** [`.cursor/commands/proofread.md`](../../commands/proofread.md)
