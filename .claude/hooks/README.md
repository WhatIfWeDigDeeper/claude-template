# Claude Code Hooks

Hooks allow you to run custom scripts in response to Claude Code events.

## Configuration

Add hooks to your `.claude/settings.json`:

```json
{
  "hooks": {
    "pre-commit": "npm run lint && npm test",
    "post-edit": "npm run format"
  }
}
```

## Available Hook Points

| Hook | Triggered When |
|------|----------------|
| `pre-commit` | Before creating a git commit |
| `post-edit` | After editing a file |
| `pre-push` | Before pushing to remote |
| `post-test` | After running tests |

## Example Hooks

### Pre-commit: Lint and Test

```json
{
  "hooks": {
    "pre-commit": "npm run lint && npm test"
  }
}
```

### Post-edit: Format Code

```json
{
  "hooks": {
    "post-edit": "npx prettier --write ${FILE}"
  }
}
```

### Pre-push: Full Validation

```json
{
  "hooks": {
    "pre-push": "npm run build && npm test && npm run test:e2e"
  }
}
```

## Environment Variables

Hooks have access to:
- `${FILE}` - The file that was edited (for post-edit)
- `${FILES}` - All files in the commit (for pre-commit)
- `${BRANCH}` - Current git branch

## Disabling Hooks

To temporarily disable hooks, users can set:
```bash
CLAUDE_SKIP_HOOKS=1 claude
```
