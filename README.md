# Roo Code Global Configuration

This repository contains global configuration files for [Roo Code](https://roocode.com), a VS Code extension that provides AI-powered development assistance. These configuration files are stored in the `~/.roo/` directory and are automatically loaded by Roo Code across all your projects.

## 📁 Repository Structure

```
~/.roo/
├── commands/          # Custom Roo commands for development workflows
├── rules/             # Global rules applied across all projects
├── .gitignore         # Standard macOS and system file exclusions
└── README.md          # This file
```

## 🎯 Purpose

This directory serves as a centralized location for:

- **Reusable Commands**: Pre-configured workflows that can be invoked from any project
- **Global Rules**: Behavioral guidelines applied to all Roo Code interactions
- **Consistent Configuration**: Maintain uniform development practices across projects

## 📋 Available Commands

Custom commands are stored in the [`commands/`](commands/) directory. Each command is a markdown file with embedded instructions for Roo Code.

### Git & Version Control

- **[`git-commit.md`](commands/git-commit.md)** - Suggests Conventional Commit messages from current changes
  - Analyzes staged or unstaged changes
  - Follows [Conventional Commits](https://www.conventionalcommits.org/) specification
  - Provides copy-ready commit messages
  - **Safety**: Read-only, never executes git commands

- **[`git-code-review.md`](commands/git-code-review.md)** - Performs comprehensive code review of git diff
  - Constructive and professional analysis of changes
  - Evaluates code quality, security, performance, and test coverage
  - Provides specific, actionable feedback prioritized by severity
  - Acknowledges strengths while identifying improvement areas
  - **Safety**: Read-only, never modifies code

### Project Memory System

- **[`init-memory-bank.md`](commands/init-memory-bank.md)** - Creates project memory bank (`memory-bank/`)
  - Scaffolds persistent project context structure with standardized templates
  - Includes `memory-bank/imports/` directory for external reference material
    - Subdirectories: `api/`, `schemas/`, `diagrams/`, `references/`
  - Creates enforcement rules in `.roo/rules/` that require consultation of memory bank
  - Includes manifest and documentation for imported references

- **[`update-active-context.md`](commands/update-active-context.md)** - Refreshes active context from recent work
  - Updates current focus and recent changes
  - Tracks next steps and open questions
  - Based on git history and repo state

- **[`update-progress.md`](commands/update-progress.md)** - Updates project progress tracking
  - Maintains completed/in-progress/planned milestones
  - Tracks known issues and tech debt
  - Syncs with git history and TODO markers

### Project Setup

- **[`init-resources.md`](commands/init-resources.md)** - Initializes `resources/` directory scaffold
  - Creates structure for reference repos, docs, snippets, and sample data
  - Includes manifest for tracking external dependencies

- **[`init-rooignore.md`](commands/init-rooignore.md)** - Generates `.rooignore` file
  - Excludes build artifacts, dependencies, logs, and secrets from AI context
  - Uses safe defaults to reduce noise
  - Never overwrites existing `.rooignore`

## 🔧 Usage

### Invoking Commands

Commands can be invoked in Roo Code using the `/` slash command syntax:

```
/git-commit
/git-code-review
/init-memory-bank
```

Roo Code automatically loads commands from `~/.roo/commands/` and makes them available in all projects.

### Creating Custom Commands

To add your own custom command:

1. Create a new markdown file in [`commands/`](commands/)
2. Add a YAML frontmatter with a `description` field:
   ```markdown
   ---
   description: "Brief description of what this command does"
   ---
   ```
3. Write the command instructions in markdown
4. Save and restart Roo Code (if necessary)

### Adding Global Rules

Global rules can be placed in the [`rules/`](rules/) directory as markdown files. These rules are automatically applied to all Roo Code interactions across all projects.

## 🛡️ Safety & Best Practices

All included commands follow strict safety principles:

- **Read-Only by Default**: Git commands never execute destructive operations
- **Explicit Confirmation**: Commands that modify files ask for confirmation
- **No Overwrites**: Initialization commands preserve existing files
- **Context-Aware**: Commands respect project-specific configuration

## 🔗 Related Resources

- [Roo Code Documentation](https://roocode.com/docs)
- [Conventional Commits Specification](https://www.conventionalcommits.org/)
- [Project Memory Pattern](https://github.com/RooVetGit/Roo-Code/discussions)

## 📝 Notes

- This directory is version-controlled to maintain consistency across machines
- Sensitive information (API keys, tokens) should never be stored here
- Commands are designed to be composable and chainable

## 🤝 Contributing

Feel free to modify these commands to suit your workflow. Common customizations include:

- Adjusting commit message conventions
- Modifying code review severity
- Adding project-specific memory templates
- Creating domain-specific commands

---

**Location**: `~/.roo/`  
**Maintained by**: Personal configuration  
**Last Updated**: 2026-01-17
