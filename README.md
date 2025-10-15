# cc-track Plugin Marketplace

**Task Review And Context Keeper - Keep your vibe coding on track** 🚅

This marketplace provides the cc-track plugin for Claude Code - a comprehensive context management and workflow optimization system that solves the fundamental problem of context loss in AI-assisted development.

## What is cc-track?

cc-track provides:
- **Task tracking** - Capture plans, validate changes, track progress across sessions
- **Context preservation** - Maintain critical information through compaction cycles
- **Workflow automation** - Git commits, GitHub issues, and PR management
- **Real-time validation** - TypeScript/linting feedback and task compliance checking
- **Cost tracking** - Custom status line showing usage and API limits

## Installation

### Prerequisites

Before installing cc-track, ensure you have:
- **Claude Code** with plugin support (October 2025+)
- **Bun runtime** 1.0.0+ - [Install Bun](https://bun.sh)
- **Git** (for task management features)
- **GitHub CLI** (optional, for GitHub integration)

Verify Bun installation:
```bash
bun --version  # Should show 1.0.0+
```

### Install cc-track

```bash
# 1. Add this marketplace (one-time setup)
/plugin marketplace add cahaseler/cc-track-marketplace

# 2. Install cc-track plugin
/plugin install cc-track@cc-track-marketplace

# 3. Install plugin dependencies
cd $(dirname $(which claude-code))/../plugins/cc-track
bun install
```

### Verify Installation

```bash
# Navigate to your project
cd /path/to/your-project

# Start Claude Code
claude-code
```

In Claude Code:
```bash
# Run setup command
/setup-cc-track

# Follow the interactive prompts to configure features
```

## Features

### Core Features (Always Available)
- **Spec-Driven Development** - `/specify`, `/clarify`, `/plan`, `/tasks` workflow
- **Task Management** - Active task tracking with progress monitoring
- **Context Preservation** - Persistent project context across sessions
- **Git Integration** - Automatic branch management and WIP commits

### Optional Features (Enable via /setup-cc-track)
- **GitHub Integration** - Automatic issue and PR creation
- **Edit Validation** - Real-time TypeScript and linting checks (blocking)
- **Branch Protection** - Prevent edits on main/master branches
- **Custom Status Line** - Shows task, costs, and API limits
- **API Timer Display** - Configurable rate limit visibility
- **WebSearch Year Validation** - Prevents outdated year searches

## Quick Start

After installation:

```bash
# 1. Run setup in your project
/setup-cc-track

# 2. Create your first feature spec
/specify "Add user authentication"

# 3. Clarify requirements
/clarify

# 4. Generate technical plan
/plan

# 5. Create task breakdown
/tasks

# 6. Start implementing!
# (Claude works through tasks, validating as you go)

# 7. When ready to complete
/prepare-completion  # Validates tests, lint, runs code review
/complete-task       # Squashes commits, creates PR
```

## Commands Reference

- `/setup-cc-track` - Initial setup wizard
- `/specify` - Create feature specification
- `/clarify` - Refine requirements
- `/plan` - Generate implementation plan
- `/tasks` - Create task breakdown
- `/prepare-completion` - Validate task readiness
- `/complete-task` - Complete task and create PR
- `/add-to-backlog` - Add ideas without disrupting work
- `/constitution` - Set project guardrails
- `/config-track` - Modify feature configuration

## Project Structure

cc-track creates a `.claude/` directory in your project:

```
your-project/
├── .claude/
│   ├── specs/             # Feature specifications
│   │   └── 001-feature/
│   │       ├── spec.md    # Requirements
│   │       ├── plan.md    # Technical design
│   │       ├── tasks.md   # Task breakdown
│   │       └── progress.md # Implementation log
│   ├── track.config.json  # Feature configuration
│   ├── product_context.md # Project vision
│   ├── system_patterns.md # Technical patterns
│   ├── decision_log.md    # Architectural decisions
│   └── ...
└── CLAUDE.md              # Main context file
```

## Configuration

Enable/disable features in `.claude/track.config.json`:

```json
{
  "features": {
    "edit_validation": { "enabled": true },
    "pre_tool_validation": { "enabled": true },
    "github_integration": {
      "enabled": true,
      "auto_create_issues": true,
      "auto_create_prs": true
    },
    "statusline": { "enabled": true },
    "api_timer": { "display": "sonnet-only" }
  }
}
```

## Migrating from npm Version

If you previously used cc-track v2.x (npm package):

```bash
# 1. Uninstall npm version
npm uninstall -g cc-track

# 2. Install plugin (follow Installation steps above)

# 3. Your .claude/ project files work unchanged!
```

See the [full migration guide](https://github.com/cahaseler/cc-track/blob/main/MIGRATION.md) for detailed instructions.

## Updates

Update cc-track to the latest version:

```bash
/plugin update cc-track
```

Claude Code handles updates automatically.

## Troubleshooting

### "Plugin dependencies not installed"

Run dependency installation:
```bash
cd $(dirname $(which claude-code))/../plugins/cc-track
bun install
```

### "Bun runtime not found"

Install Bun:
```bash
curl -fsSL https://bun.sh/install | bash
# Restart terminal
bun --version
```

### Commands not working

Verify plugin is installed:
```bash
/plugin list  # Should show cc-track
```

If not listed:
```bash
/plugin marketplace add cahaseler/cc-track-marketplace
/plugin install cc-track@cc-track-marketplace
```

### Hooks not triggering

Check configuration:
```bash
/config-track  # Enable desired features
```

Restart Claude Code after configuration changes.

## Support

- **Documentation**: [GitHub Repository](https://github.com/cahaseler/cc-track)
- **Issues**: [GitHub Issues](https://github.com/cahaseler/cc-track/issues)
- **Claude Code Docs**: [docs.anthropic.com/claude-code](https://docs.anthropic.com/en/docs/claude-code)

## License

MIT - See [LICENSE](https://github.com/cahaseler/cc-track/blob/main/LICENSE)

## About

cc-track is developed and maintained by [@cahaseler](https://github.com/cahaseler). It emerged from real-world experience with context loss and task drift in AI-assisted development, providing systematic solutions to keep development "on track." 🚅
