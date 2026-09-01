# Gemini Global Instructions & Workflows

A central repository storing global customization instructions, rules, and workflows for Google Antigravity and Gemini agents.

## Repository Structure

```
gemini-instructions/
├── GEMINI.md
├── config/
│   ├── rules/
│   │   └── python_styleguide.md
│   └── global_workflows/
│       ├── add-commit-push.md
│       ├── ask.md
│       ├── explain-issue.md
│       ├── plan.md
│       └── review-text.md
└── README.md
```

## Contents

### 1. Global Instructions (`GEMINI.md`)
Maps to `~/.gemini/GEMINI.md`. Contains global agent behavior, persona, user constraints, and default execution guidelines.

### 2. Coding Rules (`config/rules/`)
Maps to `~/.gemini/config/rules/`.
- **`python_styleguide.md`**: Supplementary Python coding rules and idiomatic standards (function visibility, modularity, nesting limits, and match/case conventions).

### 3. Global Workflows (`config/global_workflows/`)
Maps to `~/.gemini/config/global_workflows/`. These provide custom slash commands in chat interfaces:
- **`/add-commit-push`** (`add-commit-push.md`): Iterative Git staging, conventional commit generation, and remote pushing.
- **`/ask`** (`ask.md`): Concise, factual research assistant persona with strict response formatting constraints.
- **`/explain-issue`** (`explain-issue.md`): Diagnoses the root cause of an issue and proposes a concrete fix.
- **`/plan`** (`plan.md`): Activates planning mode to research, draft implementation designs, and await approval before code modifications.
- **`/review-text`** (`review-text.md`): Comprehensive text review for logical, stylistic, typographical, semantic, grammatical, and structural errors.
