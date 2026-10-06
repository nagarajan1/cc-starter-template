# cc-starter-template

A fork-and-go starter template for Claude Code projects with pre-configured safety guardrails.

## Quick Start

1. **Clone or fork this template** to get started with a new Claude Code project.
2. **Review `.claude/settings.json`** to understand the configured guardrails.
3. **Start coding** in the `src/` directory.

## Required Tools

- Node.js 20+
- Python 3.10+
- Docker
- Claude Code (authenticated)

## Project Setup

### Claude Code Configuration

This template includes `.claude/settings.json` with pre-configured guardrails:

#### Model
- **Default Model**: Claude Sonnet 5.5 (optimized for speed and quality)

#### Permissions
- ✅ **Read**: All files allowed
- ✅ **Write**: Only files under `src/` directory
- ❌ **Deny**: Destructive `rm -rf` commands

#### Security
- ❌ **Protected Files**: `.env`, `.env.*`, `secrets/` directory are not readable
- ⚠️ **Web Requests**: `WebFetch` requires explicit user approval before executing

## Directory Structure

```
.
├── .claude/
│   └── settings.json          # Claude Code configuration & guardrails
├── src/                       # Edit code here (write access enabled)
├── README.md                  # This file
└── ...
```

## Guardian Rules

| Rule | Status | Purpose |
|------|--------|---------|
| Sonnet model default | ✅ | Optimal balance of speed and capability |
| Write-access to `src/` only | ✅ | Prevent accidental modifications outside project code |
| Read `.env` and `secrets/` | ❌ | Protect sensitive credentials |
| Destructive `rm -rf` commands | ❌ | Prevent data loss |
| WebFetch requires approval | ⚠️ | Control external requests |

## Getting Started with Claude Code

1. Open Claude Code in your terminal or IDE
2. Navigate to this directory
3. Claude will use the Sonnet model and apply all configured guardrails automatically
4. Edit files in `src/` freely; other directories are protected

## Customization

To modify guardrails, edit `.claude/settings.json`. See [Claude Code documentation](https://claude.com/claude-code) for advanced configuration options.
