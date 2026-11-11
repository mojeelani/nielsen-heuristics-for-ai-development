# Nielsen's 10 Usability Heuristics
## A Practical Guide for Designing, Building, and Evaluating User Interfaces

**Independent adaptation and implementation guidance by Mohammad Jeelani (2026), HFactor Consulting — [hfactor.tech](https://hfactor.tech/).**

**Version:** 1.0 (public release)  
**Audience:** Designers, developers, product teams, usability evaluators, and AI coding assistants  
**Scope:** Project-agnostic guidance for interactive digital products

> **Attribution:** This independent guide is based on **Jakob Nielsen's 10 Usability Heuristics for User Interface Design**, published by the **Nielsen Norman Group (NN/g)**. The heuristics were refined by Nielsen in 1994 from earlier work with Rolf Molich. NN/g's article was originally published April 24, 1994, and was last reviewed January 30, 2024.
>
> **Original source:** Nielsen, J. (1994). [*10 Usability Heuristics for User Interface Design*](https://www.nngroup.com/articles/ten-usability-heuristics/). Nielsen Norman Group.  
> **Credit:** Jakob Nielsen — https://www.nngroup.com/articles/ten-usability-heuristics/

**About this guide:** The ten named heuristics below are Nielsen's framework. The implementation guidance, examples, questions, and workflow in this document are independently written applications of that framework—not a reproduction of NN/g's article, an official NN/g checklist, or an NN/g endorsement.

---

## How to use this guide

Use the ten heuristics as **evaluation lenses**, not rigid interface specifications. Each heuristic describes a broad principle of usable interaction; the right implementation depends on the user, task, platform, context, and consequences of error.

For each new or substantially changed user-facing workflow:

1. Identify the **user's task**, starting state, and intended outcome.
2. Walk through the actual interface and important alternative paths.
3. Examine the experience against **H1–H10** below, noting both strengths and potential problems.
4. Record specific, observable issues; name the relevant heuristic(s).
5. Recommend the smallest change that addresses the underlying interaction problem.
6. Verify the behavior after implementation and disclose any untested assumptions.

**Important distinctions:** A heuristic evaluation is an expert inspection, **not a substitute for watching representative users perform tasks**. These heuristics also do not establish accessibility compliance; apply relevant accessibility standards, such as [WCAG 2.2](https://www.w3.org/TR/WCAG22/), separately.

---

## The 10 heuristics

### H1 — Visibility of System Status

**Interpretation:** Users need timely, understandable information about what the product is doing and the outcome of their actions.

**Apply it:**

- Acknowledge meaningful actions promptly: saving, submitting, deleting, uploading, processing, publishing, or navigating.
- Make important states distinguishable: idle, in progress, success, partially complete, failed, and offline when applicable.
- Explain delays and show meaningful progress when available; do not imply that an operation has finished before it has.
- Keep state changes perceivable and available to assistive technologies where appropriate.
- After an action, show whether the result persisted and what, if anything, the user should do next.

**Example failure:** A user presses **Save**, sees no feedback, and presses it repeatedly because they cannot tell whether their changes were recorded.

**Evaluation question:** At every consequential moment, can the user tell what is happening, what has happened, and whether action is needed?

### H2 — Match Between the System and the Real World

**Interpretation:** The interface should reflect users' language, expectations, and task sequences rather than the system's internal architecture.

**Apply it:**

- Prefer vocabulary that intended users recognize; avoid exposing implementation jargon or internal database concepts.
- Arrange steps, fields, and information in an order that makes sense for the real task.
- Match labels and representations to what actions actually do.
- Use familiar units, examples, dates, and formats that fit the audience and locale.
- When terminology is specialized, validate it with domain users instead of assuming it is universally understood.

**Example failure:** A service dashboard requires users to choose a “resource object type” when what they understand is “appointment” or “reservation.”

**Evaluation question:** Would someone familiar with the task—but unfamiliar with the implementation—understand the terms and sequence?

### H3 — User Control and Freedom

**Interpretation:** People need practical ways to change direction, correct choices, and leave unintended states.

**Apply it:**

- Provide **Back**, **Cancel**, **Close**, **Edit**, or **Undo** where the task makes those actions meaningful.
- Distinguish reversible actions from permanent or costly ones before commitment.
- Preserve entered work when someone navigates backward or corrects a mistake, unless a clear requirement prevents it.
- Allow users to exit optional tours, dialogs, or multi-step experiences without becoming trapped.
- If a process cannot be undone, explain that constraint before the irreversible step.

**Example failure:** A multi-step form resets all entered information when the user returns to correct an earlier response.

**Evaluation question:** If the user makes the wrong choice or changes their mind, is there a clear, proportionate way out?

### H4 — Consistency and Standards

**Interpretation:** Similar things should look, sound, and behave similarly, while familiar platform conventions should remain predictable.

**Apply it:**

- Reuse established wording, navigation behaviors, form controls, feedback patterns, and component states.
- Use a single term consistently for the same object or operation; do not alternate between near-synonyms without reason.
- Follow conventional meanings of common interface patterns unless a tested reason supports deviation.
- Keep the same action in a predictable location and style across related views.
- Respect an application's existing design system and interaction patterns when they are functioning well.

**Example failure:** **Archive** hides an item in one view but permanently deletes it in another.

**Evaluation question:** Does this screen require users to relearn something they already understand elsewhere in the product or platform?

### H5 — Error Prevention

**Interpretation:** Prevent foreseeable mistakes before they occur rather than relying solely on users to repair them afterward.

**Apply it:**

- Remove invalid choices when possible and use appropriate input constraints, formats, and defaults.
- Make key requirements visible *before* the user submits or commits.
- Use confirmation for genuinely consequential actions, with enough context to prevent accidental agreement.
- Protect against accidental duplicate submissions, unintended data loss, and predictable destructive actions.
- Evaluate high-consequence errors first; low-risk actions should not be burdened with unnecessary confirmations.

**Example failure:** A form silently accepts an invalid date and fails only after the user completes several additional screens.

**Evaluation question:** Which errors are predictable here, and which can be designed out of the interaction?

### H6 — Recognition Rather than Recall

**Interpretation:** Reduce the need to remember information by making relevant context, actions, and choices visible or easy to retrieve.

**Apply it:**

- Keep field labels, current selections, and important instructions available when they are needed.
- Show users the context of their current step, especially in longer workflows.
- Provide clear option names, examples, previews, or recent selections where these support recognition.
- Avoid requiring users to memorize values from a previous screen or repeat information the system already possesses.
- Favor discoverable controls over unlabeled or ambiguous icons when meaning is uncertain.

**Example failure:** A comparison flow makes users memorize details of option A before navigating to option B.

**Evaluation question:** What does the interface ask users to remember that it could instead display or make easy to retrieve?

### H7 — Flexibility and Efficiency of Use

**Interpretation:** Support straightforward first-time use while allowing experienced users to complete frequent tasks efficiently.

**Apply it:**

- Make the essential path understandable without requiring shortcuts or advanced knowledge.
- Consider accelerators such as keyboard shortcuts, saved preferences, templates, reusable entries, and bulk actions for repetitive work.
- Allow different workable paths when tasks and user preferences genuinely differ.
- Eliminate needless repetition without hiding information needed for accurate decisions.
- Make advanced features discoverable where helpful, but avoid overwhelming beginners with them.

**Example failure:** Frequent users must re-enter the same non-sensitive settings on every visit with no way to reuse a valid prior choice.

**Evaluation question:** Is the workflow learnable for a newcomer and efficient for someone who performs it often?

### H8 — Aesthetic and Minimalist Design

**Interpretation:** Every element competes for attention. Content and visual presentation should emphasize what matters for the user's current goal.

**Apply it:**

- Establish a clear hierarchy among the task, relevant information, and available actions.
- Remove redundant explanations, decorative interruptions, and choices that add no practical value.
- Show supporting detail when it becomes relevant instead of exposing all complexity at once.
- Keep essential information visible; minimalism should not conceal critical context or functionality.
- Review each prompt, field, and confirmation for a clear task-related purpose.

**Example failure:** A simple completion screen contains multiple competing banners, secondary offers, and repetitive instructions, obscuring whether the task succeeded.

**Evaluation question:** Does each prominent element help the user understand, decide, or act—or does it dilute more important information?

### H9 — Help Users Recognize, Diagnose, and Recover from Errors

**Interpretation:** When errors do happen, communicate what went wrong in comprehensible terms and offer a useful recovery path.

**Apply it:**

- State the problem specifically in plain language; avoid relying on opaque error codes.
- Put error feedback near the affected action or field, with a summary when the layout requires one.
- Tell the user how to resolve or work around the issue when a remedy exists.
- Preserve valid input and previously completed steps after recoverable failures.
- Distinguish user-correctable input issues from technical failures and give appropriate next steps for each.

**Example failure:** After a network interruption, the product shows “Error 500” and erases the user's completed form.

**Evaluation question:** Can the user identify the problem, understand the impact, and take an informed next step?

**Distinction from H5:** H5 aims to stop avoidable errors from happening; H9 concerns diagnosis and recovery **after** an error occurs.

### H10 — Help and Documentation

**Interpretation:** A usable interface should minimize the need for explanation, but targeted assistance must be available when a task is unfamiliar or complex.

**Apply it:**

- Put concise instructions close to the task or decision they explain.
- Make additional help easy to discover and search when the experience warrants it.
- Organize help around what users want to accomplish, not internal product structure.
- Prefer actionable steps and concrete examples over lengthy general descriptions.
- Do not use documentation to excuse missing labels, confusing navigation, or preventable errors.

**Example failure:** Users must find and read a long external manual to understand a field that could be clarified with one sentence next to the input.

**Evaluation question:** When a user needs assistance, can they find brief, relevant help at the point of need?

---

## Conducting a heuristic evaluation

A heuristic evaluation should examine **realistic tasks and real interface states**, not just a static screenshot.

### 1. Define the task and coverage

Specify the target audience, primary task, entry point, expected outcome, supported platforms, and relevant constraints. Identify what views and flows are in scope.

### 2. Inspect the workflow

Walk through the normal path and relevant alternatives: first use, returning use, missing information, invalid input, cancellation, interruptions, and completion. Inspect loading, error, and empty states where applicable.

### 3. Record potential violations

For each issue, capture the screen/step, user goal, observed behavior, affected heuristic numbers, and an explanation of **why** the behavior could cause difficulty. Multiple heuristics may apply; do not manufacture ten issues merely to match ten headings.

### 4. Distinguish evidence from inference

Label whether an issue was observed in testing, reproduced in the product, inferred from an inspection, or reported by users. **Never present an expert prediction as verified user behavior.**

### 5. Prioritize issues

Use severity to guide attention, considering how often the problem may occur, how much harm or friction it creates, and whether users will repeatedly encounter it. Nielsen's separate severity-rating article describes a **0–4 scale**:

| Rating | Meaning for prioritization |
| --- | --- |
| **0** | Not considered a usability problem |
| **1** | Cosmetic issue |
| **2** | Minor issue; relatively low priority |
| **3** | Major issue; high priority |
| **4** | Serious usability breakdown requiring resolution before release |

*Scale adapted in brief from:* Jakob Nielsen, [*Severity Ratings for Usability Problems*](https://www.nngroup.com/articles/how-to-rate-the-severity-of-usability-problems/) (1994). Ratings are judgments, not measured outcomes; where possible, have multiple evaluators review and reconcile findings.

### 6. Recommend and verify changes

Propose a concrete improvement for the affected task. Re-examine the interaction after implementation, check for regressions, and record what was actually tested.

### Suggested issue format

```markdown
#### [Issue title]
- **Task / location:**
- **Heuristic(s):** H# — [heuristic name]
- **Observed behavior:**
- **Why it is a problem:**
- **Evidence type:** Reproduced / user-observed / expert inference
- **Severity:** 0–4 (with rationale)
- **Recommended change:**
- **Verification:**
```

---

## H1–H10 review checklist

Use this during a UI review, pull request, or release check. Mark an item *not applicable* when that is truly appropriate, rather than adding unnecessary UI elements to satisfy a checklist.

- [ ] **H1 — System status:** Users receive timely and truthful feedback for consequential actions.
- [ ] **H2 — Real-world match:** Terms, ordering, and representations fit user expectations.
- [ ] **H3 — Control and freedom:** Users can cancel, edit, back out, or recover where appropriate.
- [ ] **H4 — Consistency:** Controls, labels, and behaviors follow established conventions.
- [ ] **H5 — Prevention:** Foreseeable mistakes are constrained, explained, or prevented before commitment.
- [ ] **H6 — Recognition:** Users do not have to memorize context or previously shown information unnecessarily.
- [ ] **H7 — Flexibility:** Common and repeated tasks can be completed efficiently without sacrificing clarity.
- [ ] **H8 — Minimalism:** The interface prioritizes task-relevant information and actions.
- [ ] **H9 — Error recovery:** Failures are understandable, actionable, and preserve recoverable work.
- [ ] **H10 — Help:** Task-focused guidance is available at the point of need when needed.

**Coverage check:** Review relevant states and device/input modes. A successful happy-path demonstration does not establish that other states work.

---

## Guidance for Claude Code and other AI coding assistants

Treat Nielsen's heuristics as a **review framework for user-facing design choices** and changes—not as permission to redesign unrelated features or override product requirements.

When asked to implement or revise an interface:

1. **Understand:** Identify the user task, expected outcome, existing product conventions, and requested scope.
2. **Inspect:** Review the relevant screen(s) and interaction states against H1–H10. Cite heuristic identifiers only when the issue is genuinely relevant.
3. **Implement:** Make targeted improvements; preserve working flows, existing design patterns, and required business logic.
4. **Post-build review:** After implementing, inspect the resulting task and relevant states against **all H1–H10**, explicitly checking applicability rather than inventing an issue for every heuristic. Do not wait for a separate review request.
5. **Correct and verify:** Fix material issues that are clear and within scope; re-evaluate corrected flows. Exercise success, failure, cancellation, and recovery where feasible, and verify accessibility requirements separately.
6. **Report:** State which heuristics informed decisions, the post-build findings and fixes, what was actually tested, and what remains uncertain.

**Do not:**

- Assume every heuristic requires a visible feature in every screen.
- Add confirmation dialogs, onboarding, or help text without an identified user need.
- Change terminology or behavior solely for stylistic consistency when established user language differs.
- Claim heuristic compliance, validated usability, or successful accessibility testing without adequate evidence.
- Invent research findings, user preferences, product rules, test results, or outcomes.
- Introduce unrelated redesigns while implementing a narrowly scoped request.

### Optional `CLAUDE.md` integration

Place this file (`USABILITY_GUIDELINES.md`) at the root of your project, next to your project's `CLAUDE.md`. Add the following block to **your existing `CLAUDE.md`**. If the project has no `CLAUDE.md`, create one at the root.

```markdown
## Nielsen usability heuristic review

@USABILITY_GUIDELINES.md

For each new or materially revised user-facing interface:
1. Before and during implementation, consider H1–H10 and apply the relevant heuristics.
2. After implementation, **automatically perform a separate heuristic review** of the resulting task and states against all ten heuristics; check applicability and do not invent findings.
3. Correct clear in-scope issues, recheck affected interactions, and preserve project requirements.
4. Report the post-build review, actual fixes, verification performed, and untested areas.
5. Distinguish evidence from expert inference; never claim real-user validation without research.

For a complete version, use the block in `CLAUDE.example.md`.
```

**Path note:** Claude Code supports the `@path/to/file.md` import syntax inside `CLAUDE.md`. If you store the guide in `docs/` instead of the project root, write `@docs/USABILITY_GUIDELINES.md` instead. Imported content takes up context when loaded; keep the file current and consider context cost in large projects. See [Claude Code documentation](https://code.claude.com/docs/en/memory#import-additional-files).

**Keep the original project instructions:** Do not replace a project's existing `CLAUDE.md` with this entire repository's example. Merge only the relevant section so you do not lose project-specific coding and architecture guidance.

---

## Attribution and references

**The framework belongs to its original author.** This guide uses Jakob Nielsen's names and structure with explicit attribution and adds independently authored implementation guidance. It is not affiliated with or endorsed by the Nielsen Norman Group.

1. **Primary reference:** Nielsen, J. (1994, April 24; last reviewed January 30, 2024). [*10 Usability Heuristics for User Interface Design*](https://www.nngroup.com/articles/ten-usability-heuristics/). Nielsen Norman Group. **Official source:** https://www.nngroup.com/articles/ten-usability-heuristics/
2. **Evaluation method:** Moran, K., & Gordon, K. (2023, June 25). [*Heuristic Evaluations: How to Conduct*](https://www.nngroup.com/articles/how-to-conduct-a-heuristic-evaluation/). Nielsen Norman Group.
3. **Severity scale:** Nielsen, J. (1994, November 1). [*Severity Ratings for Usability Problems*](https://www.nngroup.com/articles/how-to-rate-the-severity-of-usability-problems/). Nielsen Norman Group.
4. **Complementary accessibility standard:** W3C. [*Web Content Accessibility Guidelines (WCAG) 2.2*](https://www.w3.org/TR/WCAG22/).

**Reproduction note:** The linked NN/g source retains its own copyright and reuse rules. For public distribution, link to the source and use this document's independently written examples and implementation notes; do not copy NN/g's original article text, illustrations, or posters into this repository without appropriate permission.

**Authorship and reuse:** This independently written companion guide was prepared by **Mohammad Jeelani (2026)** through **[HFactor Consulting](https://hfactor.tech/)**. Original explanations, examples, checklists, and integration guidance in this repository are shared under [CC BY 4.0](LICENSE.md). The underlying heuristics, source article, illustrations, and NN/g trademarks are not relicensed here.
