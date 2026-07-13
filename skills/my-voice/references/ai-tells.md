# AI writing tells (technical prose)

Patterns LLMs overuse in docs, blog posts, and explanations. Not a ban list; context matters. When several appear together, rewrite.

## Puffery and importance inflation

**Watch for:** pivotal, crucial, vital, testament, enduring/lasting legacy, key turning point, indelible mark, stands as, serves as a reminder, plays a vital role, underscores/highlights its importance, deep heritage

**Fix:** State what happened or what the thing does. Drop the narrator claiming significance.

| AI | Better |
|----|--------|
| "This architecture plays a pivotal role in modern platform engineering." | "This architecture owns deploy routing and preview URLs." |
| "The release is a testament to the team's dedication." | "We shipped v2 after cutting scope twice." |

## Empty `-ing` trailer phrases

**Watch for:** ensuring …, highlighting …, showcasing …, underscoring …, emphasizing …, reflecting …, contributing to …, aligning with …

Events and facts cannot "highlight" or "underscore" anything. A person can; a webhook handler cannot.

| AI | Better |
|----|--------|
| "The CLI wraps the API, ensuring a seamless developer experience." | "The CLI wraps the API and prints JSON for scripts." |
| "We added retries, contributing to improved reliability." | "We added retries; transient 5xx dropped from ~2% to under 0.1%." |

## Promotional adjectives

**Watch for:** groundbreaking, seamless, robust, cutting-edge, world-class, magical, incredible, stunning, nestled, boasts

Especially stacked: "seamless, robust, and scalable."

**Fix:** One concrete behavior or metric per claim.

## Overused LLM vocabulary

**Watch for:** delve, leverage (as verb), multifaceted, foster, realm, tapestry, landscape (figurative), navigate (figurative), holistic, synergy, paradigm

**Fix:** Plain verbs. "Use" not "leverage." "Explore" or "read" not "delve into."

## Vague uplift and transformation narratives

**Watch for:** changed how I work, game-changer, everything clicked, never looked back, more confidence, faster/easier without a before state, shapes adoption more than people admit

**Fix:** One scenario, one observation, one lesson. What was slow or opaque before? What could you see or measure after?

| AI | Better |
|----|--------|
| "This tool transformed my workflow." | "I spent less time correlating UI errors with server routes." |
| "Teams will see dramatically improved velocity." | "Our median PR-to-prod time went from days to hours on the golden path." |

## Universal claims without proof

**Watch for:** everyone, most teams, the industry, it's clear that, undoubtedly, certainly (when you lack data)

**Fix:** Narrow scope: "in my experience," "on teams I've seen," or cite a source.

## Motivational and rhetorical filler

**Watch for:** Here's the thing, At the end of the day, It all boils down to, Needless to say, In today's fast-paced world, In conclusion (when the close adds nothing)

**Fix:** Delete the sentence. Start with the claim.

## Formatting tells

- Bold on every other phrase
- Emoji in headings or bullet labels
- Long bullet lists where three sentences of prose would read cleaner
- Identical section shape repeated (Problem → Solution → Benefits → Conclusion) with thin content

**Fix:** Prose for argument; bullets for sequences, options, or checklists only.

## Rule of thumb

If you cannot point to something observable (a command, metric, log line, user action, failure mode), the sentence is probably padding. Cut or replace with specifics.
