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
| **Code Generation** | `add-feature <name and requirements>`, `add-component <name and requirements>`, `add-hook <name and requirements>`, `add-api-route <route and requirements>`, `add-test <component or area>` |
| **Maintenance** | `refactor <target>`, `update-deps [packages]`, `audit-and-fix [packages]`, `perf-audit [area]` |
| **Documentation** | `e2e-test <feature or flow>`, `document-feature <name>` |
| **Meta** | `learn` |

More details in [CLAUDE.md](../CLAUDE.md#skills-claude-can-suggest)

## Plugins

Plugins extend Claude Code with additional commands, skills, and agents. Enabled in `.claude/settings.json`:

### commit-commands

Git workflow automation:

| Command | Purpose |
|---------|---------|
| `/commit-push-pr` | Commit staged changes, push, and open a PR in one step |
| `/commit` | Create a git commit with generated message |
| `/clean_gone` | Clean up local branches deleted on remote (marked as `[gone]`) |

### code-review

| Command | Purpose |
|---------|---------|
| `/code-review` | Review a pull request for issues and improvements |

### pr-review-toolkit

Comprehensive PR review with specialized agents:

| Command | Purpose |
|---------|---------|
| `/review-pr` | Run comprehensive PR review using multiple specialized agents |

Agents (used automatically during reviews):
- `code-reviewer` - Reviews for bugs, security, and code quality
- `silent-failure-hunter` - Identifies inadequate error handling and silent failures
- `code-simplifier` - Simplifies and refines code for clarity
- `comment-analyzer` - Checks comment accuracy and maintainability
- `pr-test-analyzer` - Reviews test coverage quality
- `type-design-analyzer` - Analyzes type design for encapsulation and invariants

### feature-dev

Guided feature development:

| Command | Purpose |
|---------|---------|
| `/feature-dev` | Guided feature development with architecture focus |

Agents:
- `code-reviewer` - Reviews code for issues and conventions
- `code-explorer` - Analyzes existing features and architecture
- `code-architect` - Designs feature architectures based on existing patterns

### claude-md-management

| Command | Purpose |
|---------|---------|
| `/revise-claude-md` | Update CLAUDE.md with learnings from session |
| `/claude-md-improver` | Audit and improve CLAUDE.md files in repository |

### claude-code-setup

| Command | Purpose |
|---------|---------|
| `/claude-automation-recommender` | Analyze codebase and recommend Claude Code automations |

### frontend-design

| Command | Purpose |
|---------|---------|
| `/frontend-design` | Create distinctive, production-grade frontend interfaces |

### ralph-loop

Agentic loop for continuous development:

| Command | Purpose |
|---------|---------|
| `/ralph-loop` | Start Ralph Loop for continuous agentic development |
| `/cancel-ralph` | Cancel active Ralph Loop |
| `/help` | Explain Ralph Loop plugin |

### code-simplifier

Automatically invoked to simplify and refine code for clarity and maintainability.

### playwright

Provides browser automation tools for testing and web interaction.

### typescript-lsp

TypeScript language server integration for enhanced code intelligence.

### security-guidance

Security best practices and guidance during development.

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
