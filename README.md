# Nielsen's Usability Heuristics for AI-Assisted Development

**Independent companion guide by Mohammad Jeelani (2026), HFactor Consulting — [hfactor.tech](https://hfactor.tech/).**

**Practical, project-agnostic Markdown guidance for applying Jakob Nielsen's 10 usability heuristics while designing, coding, and reviewing user interfaces with AI assistants.**

This independent resource translates the heuristics into **implementation considerations, common failure examples, evaluation questions, review steps, and AI-coding instructions**. It is not a new framework, a substitute for usability testing, or an official Nielsen Norman Group (NN/g) publication.

> **Foundation and credit:** Jakob Nielsen, *[10 Usability Heuristics for User Interface Design](https://www.nngroup.com/articles/ten-usability-heuristics/)* (1994; reviewed in 2024), Nielsen Norman Group. The heuristics originated in earlier work by Jakob Nielsen and Rolf Molich. This repository retains the heuristic titles and identifiers while providing independently written explanations and applications. **Not affiliated with or endorsed by Jakob Nielsen or NN/g.**

## Who it's for

- Developers using Claude Code or another AI coding assistant
- UX/product designers reviewing interface decisions
- Product teams seeking a shared vocabulary for usability issues
- Evaluators preparing heuristic reviews, with or without AI assistance

## What's inside

| File | Purpose |
| --- | --- |
| [`USABILITY_GUIDELINES.md`](USABILITY_GUIDELINES.md) | H1–H10 implementation guidance, examples, review questions, evaluation process, issue template, severity ratings, and references |
| [`CLAUDE.example.md`](CLAUDE.example.md) | Two-pass build-and-review instructions to **merge** into your project's `CLAUDE.md`; includes a real `@USABILITY_GUIDELINES.md` import |
| [`EXAMPLE_PROMPTS.md`](EXAMPLE_PROMPTS.md) | Ready-to-adapt prompts for inspecting and implementing user-facing workflows |
| [`LICENSE.md`](LICENSE.md) | License for independently authored material and third-party copyright notice |

## Install with Claude Code

1. Copy **`USABILITY_GUIDELINES.md`** into the root of the application repository where you use Claude Code.
2. Open that application's **existing `CLAUDE.md`**, or create one in its project root if it does not exist.
3. Copy the usable instructions from [`CLAUDE.example.md`](CLAUDE.example.md) **into** that file. Do not overwrite existing project rules.
4. Start a fresh Claude Code session in the application repository. Use `/memory` or `/context all` to confirm that your project's instructions are visible.
5. Try: `Review the sign-up flow for usability concerns using Nielsen's heuristics. Give specific H# references, separate observed behavior from assumptions, and do not change code yet.`

### Automatic review as part of UI development

The `CLAUDE.example.md` instructions specify two passes during the **same UI task**: (1) proactively apply Nielsen's relevant heuristics while building, and (2) **after implementing, review the resulting interface against all ten heuristics**, fix clear in-scope problems, recheck, and report outcomes and limitations. You should not need to ask separately for a post-build review.

**Important distinction:** `CLAUDE.md` contains standing instructions to the assistant; it is **not a guaranteed automated quality gate**. Claude may miss a step, and a review based only on code or screenshots does not establish actual user behavior. Teams that need an enforced gate should add separate project-specific automation or review processes.

### The key import

The following line belongs in the application's actual `CLAUDE.md` (outside a Markdown code fence):

```text
@USABILITY_GUIDELINES.md
```

If the guide is at `docs/USABILITY_GUIDELINES.md`, change the line to `@docs/USABILITY_GUIDELINES.md`. Claude Code [supports imported Markdown instructions](https://code.claude.com/docs/en/memory#import-additional-files). **An example file called `CLAUDE.example.md` does not load by itself**; you must merge it into the actual `CLAUDE.md`.

**Context trade-off:** An imported guide is loaded as part of Claude Code's instruction context. You can instead point Claude to the guide and ask it to read the file only when doing a heuristic review, to avoid importing it into every session.

## The framework

| ID | Nielsen's heuristic |
| --- | --- |
| H1 | Visibility of System Status |
| H2 | Match Between the System and the Real World |
| H3 | User Control and Freedom |
| H4 | Consistency and Standards |
| H5 | Error Prevention |
| H6 | Recognition Rather than Recall |
| H7 | Flexibility and Efficiency of Use |
| H8 | Aesthetic and Minimalist Design |
| H9 | Help Users Recognize, Diagnose, and Recover from Errors |
| H10 | Help and Documentation |

See the [guide](USABILITY_GUIDELINES.md) for specific evaluation questions and implementation ideas for each heuristic.

## Review guardrails

- **Inspect actual tasks and states**, not only screenshots or visual styling.
- **Report grounded findings.** Distinguish a reproduced issue, a user-observed problem, and an expert inference.
- **Use heuristics selectively.** Not every screen needs all ten heuristics in the report.
- **Honor constraints.** Do not change unrelated flows, business logic, or established patterns without reason.
- **Do not claim validation.** A heuristic inspection is not the same as usability research with representative users; accessibility standards such as WCAG 2.2 require separate evaluation.

## Attribution and references

- **Primary:** Nielsen, J. (1994). [*10 Usability Heuristics for User Interface Design*](https://www.nngroup.com/articles/ten-usability-heuristics/). Nielsen Norman Group. ([NN/g guidance for citing the heuristics](https://www.nngroup.com/articles/ten-usability-heuristics/))
- **Method:** Moran, K., and Gordon, K. (2023). [*How to Conduct a Heuristic Evaluation*](https://www.nngroup.com/articles/how-to-conduct-a-heuristic-evaluation/). Nielsen Norman Group.
- **Prioritization:** Nielsen, J. (1994). [*Severity Ratings for Usability Problems*](https://www.nngroup.com/articles/how-to-rate-the-severity-of-usability-problems/). Nielsen Norman Group.
- **Claude Code:** [*How Claude Remembers Your Project*](https://code.claude.com/docs/en/memory). Anthropic.

## Reuse and license

The independently written guidance and examples in this repository are shared under **[Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE.md)**. The underlying heuristics and original NN/g content remain credited to their respective rights holders; our license does **not** cover NN/g's article, illustrations, posters, or trademarks.

**Independent resource created by Mohammad Jeelani through [HFactor Consulting](https://hfactor.tech/).** Contributions and adaptations are welcome with appropriate attribution to their sources.
