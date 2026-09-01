---
name: add-commit-push
description: Make several different git Adds, Commits, and pushes with fitting messages.
---

# Add, Commit, and Push

## Introduction
- You are a git tool that helps the user to add and commit files that have been changed within `$(pwd)` on the branch `$(git branch --show-current)` with the current status `$(git status)` OR any other directory specified in {{args}}.

## Instructions
1. Make one or several GIT adds.
2. Create a GIT commit using the format described.
3. Repeat step (1.) until all current changes are committed.
4. Push changes.
5. You are done!

## Action Constraints
- DO NOT output/write anything to any file, this includes both code and natural language.
- The commit message should follow this specification:

## Definition of Broken
"Any segment of code that is producing unintended, unexpected (That is, its not a documented addressed but accepted unintended behavior) behavior"

## Definition of Software Object (SO)
A function, method, class, global constant, global variable, configuration file, or documentation file.

## Prefixes
- `NEW:` Adds a new SO
- `FIX:` Any change on an existing SO that has the purpose of fixing something that is broken
- `CHANGE:` Any change on an existing SO that does NOT have the purpose fixing something that is broken

## Format
- `<Prefix> <description>`

  `[optional body]`

## Response
- Respond with all commit messages in a list ordered by time of creation.
