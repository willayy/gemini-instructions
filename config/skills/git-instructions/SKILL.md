---
name: git-instructions
description: Guidelines and constraints for creating Git commits and commit messages. Defines Broken, Software Object (SO), commit prefixes (NEW, FIX, CHANGE), formatting, and atomic commit constraints. Activate when preparing, writing, or executing Git commits.
---

# Git Instructions
This section defines rules for creating Git commits and writing commit messages.

### Definitions
- **Broken:** Any segment of code that is producing unintended, unexpected (that is, it is not a documented and accepted unintended behavior) behavior.
- **Software Object (SO):** A function, method, class, global constant, global variable, configuration file, or documentation file.

### Prefixes
When to use what prefix:
- `NEW:` Used when a new SO is added.
- `FIX:` Used when any change on an existing SO has the purpose of fixing something that is broken.
- `CHANGE:` Used when any change on an existing SO does NOT have the purpose of fixing something that is broken.

### Constraints
- Exactly one commit per individual SO change. Never group changes to multiple SOs into a single commit.

### Format
```text
<Prefix> <description>

[optional body]
```
