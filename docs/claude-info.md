# Claude Code Configuration

This project includes Claude Code configuration (skills, commands, settings) for enhanced AI-assisted development.

## Commands (User-Initiated)

Type these in Claude Code to trigger them:

| Command | Purpose |
|---------|---------|
| `/commit` | Stage changes and create commit with generated message |
| `/pr` | Create pull request with generated description |
| `/review` | Review code changes before committing |
| `/parallel-work [features...]` | Set up git worktrees for parallel feature development |
| `/integrate-parallel-work [features...]` | Merge parallel features into integration branch |
| `/parallel-agents [features...]` | Spawn subagents for parallel work |

More details in [CLAUDE.md](../CLAUDE.md#commands-user-initiated)

## Skills (Claude Suggests)

Claude will proactively suggest these when appropriate:

| Purpose | Skills |
|---------|--------|
| **Building & Fixing** | `fix-build`, `debug <issue description>` |
| **Code Generation** | `add-feature <name and description>`, `add-component <name and description>`, `add-hook <name and description>`, `add-api-route <route>`, `add-test <component or area>` |
| **Maintenance** | `refactor <target>`, `update-deps <packages?>`, `audit-and-fix <packages?>`, `perf-audit <area?>` |
| **Documentation** | `e2e-test <feature or flow>`, `document-feature <name and description>` |
| **Meta** | `learn` |

More details in [CLAUDE.md](../CLAUDE.md#skills-claude-can-suggest)

## Customization

- **settings.json**: Configure plugins and permissions
- **CLAUDE.md**: Add project-specific instructions
- **skills/**: Add or modify skill definitions
- **commands/**: Add or modify slash commands

## Assumptions

These configurations assume:

- npm for package management
- TypeScript
- Jest + React Testing Library for unit tests
- Playwright for e2e tests
- ESLint for linting

Modify the skills if your project uses different tools.
