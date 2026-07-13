# AI Personal Financial Planner

An AI agent project for personal financial planning in Australia. It combines Cursor agent skills with tooling so calculations and advice follow Australian tax, superannuation, and payroll rules.

## Features

- **Agent skills** — reusable instructions for domain-specific tasks (e.g. take-home pay calculations)
- **Australian focus** — built around ATO tax brackets, Medicare Levy, Super Guarantee, HELP/HECS, and common payroll deductions
- **Conventional commits** — Husky + commitlint enforce a consistent git history

## Agent Skills

Skills live in `.agents/skills/` and are loaded automatically by Cursor when relevant.

| Skill | Description |
|-------|-------------|
| [`calculate_take_home_pay`](.agents/skills/calculate_take_home_pay/SKILL.md) | Net salary / take-home pay for Australian residents, including tax, Medicare, super, and HELP debt |

Each skill includes trigger conditions, required inputs, calculation steps, and links to official ATO references.

## Project Structure

```
.
├── .agents/skills/       # Cursor agent skills
├── .husky/               # Git hooks (commit message linting)
├── commitlint.config.js  # Commitlint rules (Conventional Commits)
├── index.ts              # Application entry point
├── package.json
└── tsconfig.json
```

## Getting Started

### Prerequisites

- [Bun](https://bun.sh/) 1.3+

### Install

```bash
bun install
```

This installs dependencies and sets up Husky git hooks via the `prepare` script.

### Run

```bash
bun run index.ts
```

## Development

This project uses **Bun** as the runtime and package manager. See [`CLAUDE.md`](CLAUDE.md) for Bun-specific conventions used in this repo.

```bash
bun install          # Install dependencies
bun run index.ts     # Run the entry point
bun test             # Run tests
```

## Commit Messages

Commits are validated by [commitlint](https://commitlint.js.org/) through a Husky `commit-msg` hook. Messages must follow [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>[optional scope]: <subject>
```

### Allowed types

| Type | Use for |
|------|---------|
| `feat` | New feature |
| `fix` | Bug fix |
| `docs` | Documentation only |
| `style` | Formatting, whitespace (no logic change) |
| `refactor` | Code change that isn't a fix or feature |
| `perf` | Performance improvement |
| `test` | Adding or updating tests |
| `build` | Build system or dependencies |
| `ci` | CI/CD config or scripts |
| `chore` | Maintenance tasks |
| `revert` | Reverting a previous commit |

### Examples

```bash
feat: add budget tracking skill
fix(calc): correct Medicare levy threshold
docs: expand README setup section
```

### Test a message locally

```bash
echo "feat: add new skill" | bunx commitlint
```

Invalid messages (missing type, wrong casing, trailing period, etc.) are rejected before the commit is created.

## License

See [LICENSE](LICENSE).
