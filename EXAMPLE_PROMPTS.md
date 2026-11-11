# Example prompts for AI-assisted heuristic reviews

**Example prompts by Mohammad Jeelani (2026), [HFactor Consulting](https://hfactor.tech/).** Based on Jakob Nielsen's [10 usability heuristics](https://www.nngroup.com/articles/ten-usability-heuristics/).

Use these after you have copied `USABILITY_GUIDELINES.md` into your product repository. If using Claude Code, follow the setup in [`README.md`](README.md).

## 1. Inspect an existing flow (no code changes)

> Review the **[name of task flow]** using Jakob Nielsen's 10 usability heuristics as defined in `USABILITY_GUIDELINES.md`. Inspect the relevant implementation and task states. Identify *specific* usability concerns with their H# references, affected step, evidence type (reproduced versus expert inference), likely impact, and suggested fix. Do not force findings for every heuristic and do not edit code.

## 2. Build a new interface or feature

> Implement **[feature and user task]** within the existing project conventions. Use `USABILITY_GUIDELINES.md` during design decisions and apply relevant H1–H10 heuristics. Preserve the expected flow and business rules. Include appropriate system feedback, opportunities to correct input, error prevention, and recovery where warranted. After implementation, conduct a separate H1–H10 heuristic review without waiting for another prompt. Check all ten for applicability, identify grounded issues, fix clear in-scope problems, re-review the affected interactions, and report findings, fixes, tests, and limitations. Do not invent findings or claim user validation.

## 3. Prioritize findings

> Review the usability issues found in **[flow or review document]** and apply the Nielsen 0–4 severity framework described in `USABILITY_GUIDELINES.md`. For each issue, consider likely frequency, impact, and persistence; state the rationale and any uncertainty. Propose a prioritized remediation list. Do not treat severity as validated by user research unless evidence exists.

## 4. Review a pull request

> Inspect the changes in **[PR or commit]** for potential usability regressions. Focus on the changed user tasks, not unrelated code. Reference relevant Nielsen heuristic IDs from `USABILITY_GUIDELINES.md`, describe observable behavior, identify untested states, and recommend only justified fixes. Do not imply a passing heuristic review guarantees usability or accessibility.

## 5. Create a reusable issue report

> For each grounded usability concern found in **[screen/flow]**, report: issue title; user task and step; heuristic ID; observed behavior or explicit inference; user impact; severity (0–4 with rationale if justified); recommended correction; and a practical verification step. Return a concise Markdown report suitable for a GitHub issue.

**Reminder:** AI-generated heuristic findings are review hypotheses, not demonstrated facts about real users. Follow up with representative user testing when stakes, uncertainty, or design novelty justify it.
