# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

Template repository with Claude Code skills, commands, and configuration for common development tasks.

## Structure

```
.claude/
├── commands/     # User-initiated slash commands (/parallel-work, etc.)
├── skills/       # Proactive automations Claude can suggest
├── scripts/      # Automation scripts (validate-markdown.sh)
└── settings.json # Plugins and permissions
```

## Commands (User-Initiated)

- `/parallel-work [features...]` - Set up git worktrees for parallel feature development
- `/integrate-parallel-work [features...]` - Merge parallel features into integration branch
- `/parallel-agents [features...]` - Spawn subagents for parallel work

## Skills (Claude Can Suggest)

- `npm-latest <packages>` - Update packages to latest versions with validation
- `e2e-test <feature|all>` - Create Playwright e2e tests
- `document-feature <name>` - Generate technical and user documentation
- `add-test <component>` - Add Jest/React Testing Library tests
- `add-feature <name>` - Add feature with full validation in worktree
- `audit-and-fix <packages>` - Security audit and fix vulnerabilities

## Scripts

- `bash .claude/scripts/validate-markdown.sh` - Check markdown formatting

## Key Patterns

- **Worktree Isolation**: Skills use isolated worktrees at `../<name>-[timestamp]`
- **Validation Chain**: `build` → `lint` → `test` → `test:e2e`
- **Parallel Execution**: 3+ items use Task tool subagents
