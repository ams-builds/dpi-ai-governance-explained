# dpi-ai-governance-explained

**The pitch: you make an AI app or an agent. This kit tells you how much risk it has, and which controls it must have at that level of risk.**

![Six steps: you give a description of your app, Claude scores the risks, you confirm the tier, Claude drafts the controls, and you keep the evidence](assets/kit-at-a-glance.svg)

*For plain English of the technical words, refer to the [Jargon Buster](JARGON.md).*

This repository has a plain-language explainer and a Claude skill. The source is [DPI–AI Governance Artifacts](https://github.com/sankarshanmukhopadhyay/dpi-ai-governance-artifacts) by Sankarshan Mukhopadhyay. The source is a large kit for the governance of AI in public digital systems. This explainer uses one part of the kit, the risk tier method, and makes it easy to use.

## Who it is for

This kit is for vibe coders and for other persons who are not specialists. You make an AI app or an agent with a tool such as Claude. Before people use it, you must know which problems can occur. You do not need knowledge of law, audit, or governance.

The source kit is for public services, for example government agencies. The method also works for a small team. The source gives a pathway for a startup or a small team in `docs/guides/adoption-pathways.md`.

## Safe by default

1. **Claude reads and drafts first.** Claude does not change your code or your files until you approve.
2. **You decide the tier.** Claude proposes the scores and the tier. You confirm them or you change them.
3. **Claude uses the careful rule.** If a score of 12 has an input that is not sure, Claude uses the higher tier.
4. **No legal approval.** The kit gives you a structure. The kit does not make your app legal, certified, or approved.

## What it does

When you ask Claude for help with the risk of your app, the skill tells Claude to do these steps with you:

1. Find out what your app decides, and which persons the decisions affect.
2. Make a list of the risks for your app.
3. Give each risk a likelihood score and an impact score, from 1 to 5.
4. Multiply the two numbers to get the priority score of each risk.
5. Find the risk tier from the priority score.
6. List the controls that the tier must have.
7. List the evidence that shows that each control works.

The skill also tells Claude about frequent errors. For example, a team adds all of the controls without a reason, or a team keeps documents that no person reads.

## How it works

*The diagrams below use the visual language of [cathrynlavery/diagram-design](https://github.com/cathrynlavery/diagram-design):*

![Likelihood times impact gives a priority score from 1 to 25. The score bands give Tier 0 to Tier 3, with a special rule for a score of 12](assets/score-to-tier.svg)

Each risk gets two numbers from 1 to 5. Likelihood tells how frequently the problem can occur. Impact tells how bad the result is for people. The product of the two numbers is the priority score. A score of 0 to 11 is Tier 0, and a score of 20 or more is Tier 3.

The source gives an example. An agent that acts without a clear legal authority gets 4 × 5 = 20. That is Tier 3.

![Four columns, one for each tier. Each column lists the controls that the tier must have and the persons who review the system at that tier](assets/what-each-tier-needs.svg)

Each tier has a set of controls. Tier 0 must have only logs and traceability. Tier 3 must have a person who confirms decisions, a formal appeal for affected people, and an independent audit. A higher tier also sends the review to a wider group.

The source does not tell you that a higher tier includes the controls of the lower tiers. This explainer does not add that rule.

## How to install

**Claude chat, Claude Cowork, and the Claude apps**: upload `SKILL.md` as a custom skill. That is all.

*Developers who use Claude Code can also put this folder in a skills directory.*

## How to use it

After you install the skill, speak to Claude as usual:

- "Find the risk tier of my AI app."
- "Which controls must my agent have?"
- "Score the risks of this new feature."

The skill starts automatically. You do not need to use its name.

## Credit and license

This explainer is based on **DPI–AI Governance Artifacts**, version 1.2.0 (released 2026-10-01), by Sankarshan Mukhopadhyay: <https://github.com/sankarshanmukhopadhyay/dpi-ai-governance-artifacts>.

This is an independent plain-language explainer. It is not an official part of the source project, and the source author did not review it.

What I changed:

1. I wrote a plain-language explanation of the risk tier method in Simplified Technical English.
2. I made three new diagrams.
3. I wrote a Claude skill (`SKILL.md`) that applies the method to an app or an agent.
4. I used only a small part of the source. Most of the source kit is not in this repository.

The source uses the Creative Commons Attribution-ShareAlike 4.0 International license (CC BY-SA 4.0). This repository uses the same license, as the ShareAlike term tells. Refer to [LICENSE](LICENSE) and [NOTICE.md](NOTICE.md).

---

*For plain English of new words, refer to the [Jargon Buster](JARGON.md). It has risk tier, priority score, decision receipt, evidence bundle, and more.*
