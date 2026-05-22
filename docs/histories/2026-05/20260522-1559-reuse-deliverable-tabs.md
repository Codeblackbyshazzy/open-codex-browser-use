## [2026-05-22 15:59] | Task: Reuse deliverable tabs

### 🤖 Execution Context

- **Agent ID**: `Codex`
- **Base Model**: `GPT-5`
- **Runtime**: `Codex CLI`

### 📥 User Query

> 调整 Open Browser Use skill 说明：连续相关任务不应每次新开重复 tab，而应能从已完成分组里找回已有 tab 继续使用。

### 🛠 Changes Overview

**Scope:** `skills/open-browser-use`

**Key Actions:**

- **[Skill guidance]**: Added a core workflow step requiring agents to inspect existing user tabs before opening a new tab.
- **[Tab lifecycle]**: Documented that related follow-up tasks should claim matching tabs from `✅ Open Browser Use` or handoff groups and finalize them back as deliverables when appropriate.
- **[Release]**: Bumped runtime/package versions to `0.1.40` and added the user-facing release note.

### 🧠 Design Intent (Why)

连续相关任务经常指向同一个页面。明确要求先查找并 claim 已有 deliverable / handoff tab，可以避免完成分组里持续堆积重复页面，同时仍保留无明确匹配时新开 tab 的安全边界。

### 📁 Files Modified

- `skills/open-browser-use/SKILL.md`
- `docs/releases/feature-release-notes.md`
- `cmd/open-browser-use/main.go`
- `apps/chrome-extension/manifest.json`
- `packages/*/package.json`
- `packages/open-browser-use-python/pyproject.toml`
