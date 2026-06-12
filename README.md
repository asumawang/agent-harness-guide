# Building Effective Agent Harnesses

*A practical guide to the environment that surrounds an autonomous coding agent.*

A **harness** is everything around the model: the loop that runs it, the files it reads and writes, the tools it can call, the checks that reject its bad output, and the sandbox that contains it. The model writes the code. **The harness decides whether that code can succeed.**

[Read the guide](building-effective-agent-harnesses.md)

---

## Who this is for

Working engineers - from someone standing up their first single-agent loop to a team scaling toward multi-agent orchestration. It assumes you can read a shell script and have shipped software; it does not assume you have ever run an agent unattended.

## How to use it

- **First harness, this week:** read [Parts I-II](building-effective-agent-harnesses.md#part-i--first-principles) (the lens: first principles and matching the harness to your task), then stand up the minimal loop from [Appendix A](building-effective-agent-harnesses.md#appendix-a--the-minimal-rung-1-loop) with the task schema, session prompt, and init script from the other appendices. Stop there until it fails in a way you can name.
- **Scaling up:** Parts III-XIII in order, with the [failure-mode table](building-effective-agent-harnesses.md#common-failure-modes--a-quick-reference) as your review checklist.

Every practice in the guide is **conditional** - on your task type and your model's current ceiling. Don't adopt the whole thing by default; add structure only when you can point to the specific failure it prevents.

## What's inside

|                    |                                                                                                                                                                                  |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Parts I-II**     | First principles; matching the harness to your task                                                                  |
| **Parts III-V**    | Architecture ladder (one loop -> roles -> agents), durable state on disk, the session loop                                                                                         |
| **Parts VI-VII**   | The feedback engine: verification oracles, flaky-oracle discipline, evaluators, mechanical enforcement                                                                           |
| **Parts VIII-IX**  | Context economy and real cost numbers; prompting the harness                                                                                                                     |
| **Parts X-XI**     | Sandboxing and prompt-injection discipline; recovery and resilience                                                                                                              |
| **Parts XII-XIII** | The human side (review, steering, teams); measuring and evolving the harness                                                                                                     |
| **Appendices A-G** | Copy-pasteable artifacts: minimal loop script, task-state schema + validator, session prompt, worked evaluator criterion, progress-log template, `init.sh`, `AGENTS.md` skeleton |

## Provenance, honestly

This guide is a **synthesis of published field reports** - primarily from [Anthropic](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents) ([2](https://www.anthropic.com/engineering/harness-design-long-running-apps)), [OpenAI](https://openai.com/index/harness-engineering/), and [Geoffrey Huntley](https://ghuntley.com/ralph/) - plus critique and a few clearly-marked additions of its own. The substantive ideas belong to those sources; full attribution is in the [references](building-effective-agent-harnesses.md#references). Claims resting on a single team's experience are flagged as such in the text, and citations were last verified against the live sources in **June 2026**.

## A perishable document

The guide's own first principle applies to itself: every harness component is a bet on a *current* model weakness, and those bets expire. This was written against the models of mid-2026 and **will age**. Treat it as a well-grounded starting point to adapt and measure - not a recipe to follow blindly. If you're reading this long after the last commit, read it skeptically.

## Contributing

Issues and PRs are welcome, especially:

- **Corrections** - anything inaccurate, stale, or contradicted by newer published work *where it changes a recommendation*.
- **Field reports** - you ablated a component, measured the result, and learned something. That's exactly the evidence this guide runs on.
- **Source verification** - confirming or contesting attributed claims against the primary sources.

Please keep the house style: claims scoped to their evidence, single-source anecdotes flagged as such, no invented mechanisms for behaviors whose causes aren't established, and no confident "best practices" without the conditions under which they hold. By submitting a contribution, you agree to license it under the project's CC BY 4.0 license.

## License

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) - share and adapt freely, with attribution. Derivative versions must indicate that changes were made. See [LICENSE](LICENSE).
