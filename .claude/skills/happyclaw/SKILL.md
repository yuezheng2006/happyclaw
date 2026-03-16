---
name: happyclaw-conventions
description: Development conventions and patterns for happyclaw. TypeScript Hono project with freeform commits.
---

# Happyclaw Conventions

> Generated from [yuezheng2006/happyclaw](https://github.com/yuezheng2006/happyclaw) on 2026-03-16

## Overview

This skill teaches Claude the development patterns and conventions used in happyclaw.

## Tech Stack

- **Primary Language**: TypeScript
- **Framework**: Hono
- **Architecture**: type-based module organization
- **Test Location**: separate

## When to Use This Skill

Activate this skill when:
- Making changes to this repository
- Adding new features following established patterns
- Writing tests that match project conventions
- Creating commits with proper message format

## Commit Conventions

Follow these commit message conventions based on 8 analyzed commits.

### Commit Style: Free-form Messages

### Prefixes Used

- `fix`

### Message Guidelines

- Average message length: ~42 characters
- Keep first line concise and descriptive
- Use imperative mood ("Add feature" not "Added feature")


*Commit message example*

```text
chore: trigger GitHub merge status refresh
```

*Commit message example*

```text
feat: 结构化调用轨迹展示 + 过滤 IM 过程文本 (#129)
```

*Commit message example*

```text
fix: prevent web messages from broadcasting to IM channels (#99)
```

*Commit message example*

```text
功能: 容器镜像预装 feishu-cli 二进制和 Skills
```

*Commit message example*

```text
优化: 提取 sendWsError 辅助函数消除 WS 错误发送重复代码
```

*Commit message example*

```text
优化: 修复分享图片 Observer 泄漏 + 懒加载 ShareImageDialog
```

*Commit message example*

```text
Merge pull request #190 from lgy1159/fix/security-hardening
```

*Commit message example*

```text
修复: DOMPurify 添加 FORBID_TAGS + WS 权限校验错误反馈
```

## Architecture

### Project Structure: Single Package

This project uses **type-based** module organization.

### Source Layout

```
src/
├── middleware/
├── routes/
```

### Entry Points

- `src/index.ts`

### Configuration Files

- `.prettierrc`
- `container/Dockerfile`
- `container/agent-runner/package.json`
- `container/agent-runner/tsconfig.json`
- `package.json`
- `tsconfig.json`
- `web/package.json`
- `web/tsconfig.json`
- `web/vite.config.ts`

### Guidelines

- Group code by type (components, services, utils)
- Keep related functionality in the same type folder
- Avoid circular dependencies between type folders

## Code Style

### Language: TypeScript

### Naming Conventions

| Element | Convention |
|---------|------------|
| Files | PascalCase |
| Functions | camelCase |
| Classes | PascalCase |
| Constants | SCREAMING_SNAKE_CASE |

### Import Style: Relative Imports

### Export Style: Named Exports


*Preferred import style*

```typescript
// Use relative imports
import { Button } from '../components/Button'
import { useAuth } from './hooks/useAuth'
```

*Preferred export style*

```typescript
// Use named exports
export function calculateTotal() { ... }
export const TAX_RATE = 0.1
export interface Order { ... }
```

## Error Handling

### Error Handling Style: Try-Catch Blocks

A **global error handler** catches unhandled errors.


*Standard error handling pattern*

```typescript
try {
  const result = await riskyOperation()
  return result
} catch (error) {
  console.error('Operation failed:', error)
  throw new Error('User-friendly message')
}
```

## Common Workflows

These workflows were detected from analyzing commit patterns.

### Database Migration

Database schema changes with migration files

**Frequency**: ~4 times per month

**Steps**:
1. Create migration file
2. Update schema definitions
3. Generate/update types

**Files typically involved**:
- `**/schema.*`
- `**/types.ts`

**Example commit sequence**:
```
功能: 一键 Bug 报告 — 侧边栏入口 + Claude 分析 + GitHub Issue 提交
Merge remote-tracking branch 'origin/main' into fix/sub-conversation-duplicate-messages
修复: Bug 报告交互优化 — 有 gh 账号时直接提交 + JSON 解析修复
```

### Bug Report Feature Workflow

Implements or improves the one-click bug report feature, including backend API, frontend dialog, toast notifications, and schema updates.

**Frequency**: ~2 times per month

**Steps**:
1. Edit or add src/routes/bug-report.ts to implement backend endpoints.
2. Update src/schemas.ts for API validation.
3. Modify src/web.ts for backend integration.
4. Update or create web/src/components/common/BugReportDialog.tsx for frontend dialog.
5. Edit web/src/components/layout/NavRail.tsx to add or update sidebar entry.
6. Update web/src/components/settings/AboutSection.tsx for documentation or entry.
7. Edit web/src/utils/toast.ts to enhance toast notifications.

**Files typically involved**:
- `src/routes/bug-report.ts`
- `src/schemas.ts`
- `src/web.ts`
- `web/src/components/common/BugReportDialog.tsx`
- `web/src/components/layout/NavRail.tsx`
- `web/src/components/settings/AboutSection.tsx`
- `web/src/utils/toast.ts`

**Example commit sequence**:
```
Edit or add src/routes/bug-report.ts to implement backend endpoints.
Update src/schemas.ts for API validation.
Modify src/web.ts for backend integration.
Update or create web/src/components/common/BugReportDialog.tsx for frontend dialog.
Edit web/src/components/layout/NavRail.tsx to add or update sidebar entry.
Update web/src/components/settings/AboutSection.tsx for documentation or entry.
Edit web/src/utils/toast.ts to enhance toast notifications.
```

### Streaming Agent Runner Fix Workflow

Fixes or improves agent-runner and streaming message handling, often addressing race conditions, timeouts, or memory leaks across backend and frontend.

**Frequency**: ~3 times per month

**Steps**:
1. Edit container/agent-runner/src/index.ts for runner logic.
2. Modify src/group-queue.ts for queue/task management.
3. Update src/index.ts for core streaming logic.
4. Edit web/src/components/chat/StreamingDisplay.tsx for frontend streaming UI.
5. Update web/src/stores/chat.ts for frontend state management.

**Files typically involved**:
- `container/agent-runner/src/index.ts`
- `src/group-queue.ts`
- `src/index.ts`
- `web/src/components/chat/StreamingDisplay.tsx`
- `web/src/stores/chat.ts`

**Example commit sequence**:
```
Edit container/agent-runner/src/index.ts for runner logic.
Modify src/group-queue.ts for queue/task management.
Update src/index.ts for core streaming logic.
Edit web/src/components/chat/StreamingDisplay.tsx for frontend streaming UI.
Update web/src/stores/chat.ts for frontend state management.
```

### File Download Blob Fix Workflow

Migrates or fixes file download logic to use fetch+blob for better compatibility, especially on iOS/PWA, and adds user-visible error handling.

**Frequency**: ~2 times per month

**Steps**:
1. Edit web/src/components/chat/FilePanel.tsx for download logic.
2. Modify web/src/components/chat/ShareImageDialog.tsx if image download is involved.
3. Add or update web/src/utils/download.ts for unified download helpers.

**Files typically involved**:
- `web/src/components/chat/FilePanel.tsx`
- `web/src/components/chat/ShareImageDialog.tsx`
- `web/src/utils/download.ts`

**Example commit sequence**:
```
Edit web/src/components/chat/FilePanel.tsx for download logic.
Modify web/src/components/chat/ShareImageDialog.tsx if image download is involved.
Add or update web/src/utils/download.ts for unified download helpers.
```

### Mermaid Svg Xss Protection Workflow

Adds or enhances XSS protection for Mermaid SVG rendering, including DOMPurify integration and package updates.

**Frequency**: ~2 times per month

**Steps**:
1. Edit web/src/components/chat/MermaidDiagram.tsx to add or update DOMPurify logic.
2. Update web/package.json and web/package-lock.json to add/upgrade dependencies.

**Files typically involved**:
- `web/src/components/chat/MermaidDiagram.tsx`
- `web/package.json`
- `web/package-lock.json`

**Example commit sequence**:
```
Edit web/src/components/chat/MermaidDiagram.tsx to add or update DOMPurify logic.
Update web/package.json and web/package-lock.json to add/upgrade dependencies.
```

### Websocket Error Feedback Workflow

Improves WebSocket error handling by adding error feedback to users and updating types and frontend display.

**Frequency**: ~2 times per month

**Steps**:
1. Edit src/types.ts to add new ws_error type.
2. Update src/web.ts to send ws_error events.
3. Modify web/src/components/chat/ChatView.tsx to display error feedback.

**Files typically involved**:
- `src/types.ts`
- `src/web.ts`
- `web/src/components/chat/ChatView.tsx`

**Example commit sequence**:
```
Edit src/types.ts to add new ws_error type.
Update src/web.ts to send ws_error events.
Modify web/src/components/chat/ChatView.tsx to display error feedback.
```


## Best Practices

Based on analysis of the codebase, follow these practices:

### Do

- Use PascalCase for file names
- Prefer named exports

### Don't

- Don't deviate from established patterns without discussion

---

*This skill was auto-generated by [ECC Tools](https://ecc.tools). Review and customize as needed for your team.*
