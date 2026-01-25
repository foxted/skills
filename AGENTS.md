# AGENTS.md

This file provides guidance to AI coding agents (Claude Code, Cursor, Copilot, etc.) when working with code in this repository.

## Repository Overview

A collection of skills for AI coding agents. Skills are packaged instructions and scripts that extend agent capabilities.

## Creating a New Skill

### Directory Structure

```
skills/
 {skill-name}/ # kebab-case directory name
 SKILL.md # Required: skill definition
 scripts/ # Optional: executable scripts
 references/ # Optional: additional documentation
 assets/ # Optional: templates, images, data files
```

### Naming Conventions

- **Skill directory**: `kebab-case` (e.g., `conventional-commits`, `log-monitor`)
- **SKILL.md**: Always uppercase, always this exact filename
- **Scripts**: `kebab-case.sh` (e.g., `deploy.sh`, `fetch-logs.sh`)
- **Zip file**: Must match directory name exactly: `{skill-name}.zip`

### SKILL.md Format

The `SKILL.md` file must contain YAML frontmatter followed by Markdown content.

**Required Frontmatter:**

```markdown
---
name: { skill-name }
description:
  {
    One sentence describing what the skill does and when to use it. Include trigger phrases like "Deploy my app",
    "Check logs",
    etc.,
  }
---
```

**Field Constraints:**

- `name`:
  - Must be 1-64 characters
  - Lowercase letters, numbers, and hyphens only (`a-z`, `0-9`, `-`)
  - Must not start or end with hyphen
  - Must not contain consecutive hyphens (`--`)
  - Must match the parent directory name
- `description`:
  - Must be 1-1024 characters
  - Should describe both what the skill does and when to use it
  - Should include specific keywords that help agents identify relevant tasks

**Optional Frontmatter Fields:**

- `license` - License name or reference to bundled license file
- `compatibility` - Environment requirements (max 500 chars)
- `metadata` - Key-value mapping for additional metadata
- `allowed-tools` - Space-delimited list of pre-approved tools (experimental)

**Body Content:**

The Markdown body after the frontmatter contains the skill instructions. There are no format restrictions - write whatever helps agents perform the task effectively.

Recommended sections:

- Step-by-step instructions
- Examples of inputs and outputs
- Common edge cases
- File references to scripts, references, or assets directories

**Example:**

````markdown
---
name: pdf-processing
description: Extract text and tables from PDF files, fill forms, merge documents. Use when working with PDF documents or when the user mentions PDFs, forms, or document extraction.
---

# PDF Processing

## How It Works

1. Load the PDF file
2. Extract text using pdfplumber
3. Process tables if present
4. Return structured data

## Examples

See [the reference guide](references/REFERENCE.md) for detailed examples.

Run the extraction script:

```bash
scripts/extract.py input.pdf
```
````

### Best Practices for Context Efficiency

Skills are loaded on-demand — only the skill name and description are loaded at startup. The full `SKILL.md` loads into context only when the agent decides the skill is relevant. To minimize context usage:

- **Keep SKILL.md under 500 lines** — put detailed reference material in separate files
- **Write specific descriptions** — helps the agent know exactly when to activate the skill
- **Use progressive disclosure** — reference supporting files that get read only when needed
- **Prefer scripts over inline code** — script execution doesn't consume context (only output does)
- **File references work one level deep** — link directly from SKILL.md to supporting files

### Script Requirements (Optional)

If you include scripts in the `scripts/` directory:

- Be self-contained or clearly document dependencies
- Include helpful error messages
- Handle edge cases gracefully
- Supported languages depend on the agent implementation (commonly Python, Bash, JavaScript)
- Reference scripts using relative paths from SKILL.md: `scripts/{script-name}.sh`

### File References

When referencing other files in your skill, use relative paths from the skill root:

```markdown
See [the reference guide](references/REFERENCE.md) for details.
Run the extraction script: `scripts/extract.py`
```

Keep file references one level deep from `SKILL.md`. Avoid deeply nested reference chains.

### Validation

Use the [skills-ref](https://github.com/agentskills/agentskills/tree/main/skills-ref) reference library to validate your skills:

```bash
skills-ref validate ./{skill-name}
```

This checks that your `SKILL.md` frontmatter is valid and follows all naming conventions.
