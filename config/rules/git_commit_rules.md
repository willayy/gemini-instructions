# Git Commit Rules

**Definition of Broken:**
"Any segment of code that is producing unintended, unexpected (That is, its not a documented addressed but accepted unintended behavior) behavior"

**Definition of Software Object (SO):**
A function, method, class, global constant, global variable, configuration file, or documentation file.

**Prefixes:**
- `NEW:` Adds a new SO
- `FIX:` Any change on an existing SO that has the purpose of fixing something that is broken
- `CHANGE:` Any change on an existing SO that does NOT have the purpose fixing something that is broken

**Format:**
```text
<Prefix> <description>

[optional body]
```
