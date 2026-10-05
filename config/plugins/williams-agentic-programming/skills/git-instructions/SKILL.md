---
name: git-instructions
description: Contains Git rules that must be followed when staging files, creating Git commits, or writing commit messages.
---

# Git Instructions
This section defines rules for creating Git commits and writing commit messages based on the Conventional Commits specification.

### Definitions
- **Broken:** Any segment of code that is producing unintended, unexpected (that is, it is not a documented and accepted unintended behavior) behavior.
- **Software Object (SO):** A function, method, class, global constant, global variable, configuration file, or documentation file.

### Prefixes (Types)
When to use what type:
- `feat:` Used when a new SO is added (written).
- `fix:` Used when any change on an existing SO has the purpose of fixing something that is broken.
- `refactor:` Used when any change on an existing SO does NOT have the purpose of fixing something that is broken. This includes moving, relocating, or refactoring existing code without changing external behavior.
- `docs:` Used when a documentation SO is added or modified.
- `test:` Used when adding or modifying test SOs.
- `chore:` Used for configuration file SOs, build scripts, or dependency maintenance.
- `perf:` Used for a code change on an existing SO that improves performance.

### Description
The `<description>` must be written in lowercase imperative mood and must start with one of the following allowed verbs:
- `add`
- `allow`
- `enforce`
- `extract`
- `move`
- `prevent`
- `remove`
- `rename`
- `swap`
- `update`

### Constraints
- Exactly one commit per individual SO change. Never group changes to multiple SOs into a single commit.

### Format
```text
<type>(scope): <description>

[optional body]
```

### Examples
```text
feat(auth): add verify_token method
fix(parser): prevent null reference when input is empty
refactor(models): move user_validator to separate module
refactor(auth): rename user_token to auth_token
refactor(cache): swap redis_client with memcached_client
docs(readme): add installation instructions
```
