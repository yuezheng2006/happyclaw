---
name: bug-report-feature-workflow
description: Workflow command scaffold for bug-report-feature-workflow in happyclaw.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /bug-report-feature-workflow

Use this workflow when working on **bug-report-feature-workflow** in `happyclaw`.

## Goal

Implements or improves the one-click bug report feature, including backend API, frontend dialog, toast notifications, and schema updates.

## Common Files

- `src/routes/bug-report.ts`
- `src/schemas.ts`
- `src/web.ts`
- `web/src/components/common/BugReportDialog.tsx`
- `web/src/components/layout/NavRail.tsx`
- `web/src/components/settings/AboutSection.tsx`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit or add src/routes/bug-report.ts to implement backend endpoints.
- Update src/schemas.ts for API validation.
- Modify src/web.ts for backend integration.
- Update or create web/src/components/common/BugReportDialog.tsx for frontend dialog.
- Edit web/src/components/layout/NavRail.tsx to add or update sidebar entry.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.