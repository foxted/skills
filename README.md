# Agent Skills

A collection of skills for AI coding agents. Skills are packaged instructions and scripts that extend agent capabilities.

Skills follow the [Agent Skills](https://agentskills.io/) format.

## Available Skills

### conventional-commits

Ensures commit messages follow conventional commit format with proper type, scope, and description. Helps maintain consistent commit history across projects.

**Use when:**

- Generating commit messages
- Reviewing staged changes
- User asks for help writing commit messages
- Setting up commit message conventions for a project

**Features:**

- Supports all standard conventional commit types (feat, fix, docs, chore, refactor, test, style, perf, ci, build)
- Optional scope support for monorepo projects
- Clear guidelines for commit message formatting
- Examples of good and bad commit messages

**Commit Format:**

```
type(scope): description

[optional body]

[optional footer]
```

**Examples:**

```
feat: introduce editors field for enhanced content management
fix(clients): resolve form validation issue
docs: add AI Elements skill for manual component installation
```

## Installation

```bash
npx add-skill whatdafox/agent-skills
```

## Usage

Skills are automatically available once installed. The agent will use them when relevant tasks are detected.

**Examples:**

```
Help me write a commit message for these changes
```

```
Review my staged changes and suggest a commit message
```

```
Set up conventional commits for this project
```

## Skill Structure

Each skill contains:

- `SKILL.md` - Instructions for the agent
- `scripts/` - Helper scripts for automation (optional)
- `references/` - Supporting documentation (optional)

## License

MIT
