---
name: streaming-agent-runner-fix-workflow
description: Workflow command scaffold for streaming-agent-runner-fix-workflow in happyclaw.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /streaming-agent-runner-fix-workflow

Use this workflow when working on **streaming-agent-runner-fix-workflow** in `happyclaw`.

## Goal

Fixes or improves agent-runner and streaming message handling, often addressing race conditions, timeouts, or memory leaks across backend and frontend.

## Common Files

- `container/agent-runner/src/index.ts`
- `src/group-queue.ts`
- `src/index.ts`
- `web/src/components/chat/StreamingDisplay.tsx`
- `web/src/stores/chat.ts`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit container/agent-runner/src/index.ts for runner logic.
- Modify src/group-queue.ts for queue/task management.
- Update src/index.ts for core streaming logic.
- Edit web/src/components/chat/StreamingDisplay.tsx for frontend streaming UI.
- Update web/src/stores/chat.ts for frontend state management.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.