# Claude Code usability instructions — example

**Companion instructions by Mohammad Jeelani (2026), [HFactor Consulting](https://hfactor.tech/).** Based on Jakob Nielsen's 10 usability heuristics; see the [original NN/g source](https://www.nngroup.com/articles/ten-usability-heuristics/).

> **Installation:** Merge the section below into the **actual** `CLAUDE.md` at the root of your application project, then copy `USABILITY_GUIDELINES.md` alongside it. This example file is a template; Claude Code does **not** automatically load `CLAUDE.example.md`.
>
> If an existing project already has `CLAUDE.md`, **preserve** its other instructions. Add only the section below.

## Nielsen usability heuristics (H1–H10)

@USABILITY_GUIDELINES.md

Apply the imported, independently authored companion guide to Jakob Nielsen's 10 usability heuristics to **every task that creates, implements, or materially changes a user-facing interface or interaction**. Use this workflow as part of the same development task; do not wait for a separate user prompt to request a heuristic review.

### Pass 1 — Before and during implementation

1. Identify the intended user task, success conditions, user context, affected flow, and scope.
2. Inspect existing UI conventions and available states (loading, empty, success, errors, cancellation, and recovery). Do not invent missing requirements or research evidence.
3. Consider all ten heuristics (H1–H10) and **apply the relevant ones** while choosing layouts, terminology, controls, interactions, and feedback. Do not force every heuristic into every feature.
4. Implement narrowly within the user's requested scope. Preserve existing design-system patterns, business rules, and architecture unless a justified change is needed.
5. Run available checks and exercise the changed interaction states when tooling permits. If the UI cannot be executed or observed, say so; code inspection alone is not proof of runtime usability.

### Pass 2 — Mandatory post-implementation heuristic review

**After the UI change is implemented, and before reporting completion, perform a separate review of the resulting interface or flow against H1–H10 automatically.** Do this even when the user did not explicitly request a usability audit. This applies to new user-facing features and material UI changes, not backend-only tasks or documentation-only edits.

1. Trace the changed user task end-to-end, including applicable loading, empty, success, error, cancel, and recovery states.
2. **Check every heuristic H1–H10 for applicability.** For each, decide whether there is a grounded concern, no concern observed, or insufficient evidence/not applicable. Do not invent issues to fill the list.
3. For each material concern, record the task/step, heuristic ID, specific observation or code evidence, likely user impact, and recommended correction. Label inferences separately from reproduced behavior or user-observed evidence.
4. Use a Nielsen-style severity rating of 0–4 only when the rationale and available evidence justify it. State uncertainty.
5. **Fix clear, in-scope issues before finalizing**, then recheck the affected interaction and heuristic. Do not make broad redesigns or change business logic without authorization; surface out-of-scope or uncertain recommendations instead.
6. Run or rerun appropriate tests, type checks, accessibility checks, or manual interaction checks when available. Report exactly what was and was not verified; heuristic review does not establish WCAG compliance or usability with real users.

### Completion report

For UI tasks, include a concise **Post-build Nielsen heuristic review** in the final response:

- **Coverage:** The flow, screens, states, and verification methods reviewed.
- **H1–H10:** Briefly indicate which heuristics were relevant and whether concerns were found; group no-issue/not-applicable entries to avoid repetitive padding.
- **Findings and fixes:** List actual issues by heuristic ID, what you fixed, and what remains unresolved. Say **“No material issues identified in the inspected scope”** only if you completed the review.
- **Limitations:** Identify untested states, unsupported assumptions, and any need for real-user validation.

For a **review-only request**, perform the heuristic review but do not edit code unless the user asks for changes. For backend-only work and changes without user-facing effects, a post-build UI audit is not required.

> **Important:** This `CLAUDE.md` block is a standing instruction intended to trigger a review during the same task, not a deterministic software enforcement mechanism. It cannot guarantee that Claude will always run the review. An enforced workflow would need separate automation or hooks and appropriate project-specific verification.

> If you keep the guide under `docs/`, change the import path accordingly. See `README.md` for installation details.
