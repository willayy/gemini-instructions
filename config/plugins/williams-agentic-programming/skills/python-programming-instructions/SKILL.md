---
name: python-programming-instructions
description: Contains Python coding rules that must be followed when writing, editing, reviewing, or refactoring Python code.
---

# Python Programming Instructions

This styleguide aims to be a complement to the PEP styleguides & unwritten idiomatic Python rules supplementing any gaps that they leave and as such they have precedence over any rule defined in this style guide.

- **Public functions:** Functions without a leading underscore represent public API.
- **Private functions:** Prefix module-private functions with a leading underscore (`_`).
- **Inner helpers:** Inner helper functions should be written like public functions since their visibility is limited by default.
- **Module cohesion:** Modules should represent cohesive units of functionality, grouping related functions, classes, and constants that serve a common responsibility. Expose related public functions and classes that belong together logically.
- **Package responsibility:** Packages group related modules into a cohesive subsystem or domain, organizing the module hierarchy and exposing the subsystem's unified public interface.
- **Conditional branching:** Use `match`/`case` statements for equality checks where a variable can have multiple discrete values. Use `if` statements for testing the boolean value of other conditional logic.
