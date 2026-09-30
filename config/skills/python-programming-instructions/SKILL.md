---
name: python-programming-instructions
description: Contains Python coding rules that must be followed when writing, editing, reviewing, or refactoring Python code.
---

# Python Programming Instructions

This styleguide aims to be a complement to the PEP styleguides & unwritten idiomatic Python rules supplementeting any gaps that they leave and as such they have precedence over any rule defined in this style guide.

**Rules:**
- Normally named functions means public functions.
- _ means module private functions.
- Inner helper functions should always be written like a public functions since its visibility is limited by default.
- Each file (module) should only do one thing meaning it should generally only expose 1 public function. The only time it shouldnt is if there is very similar functionality that cant be included via paramaters.
- Use Match/Case statements for equality checks where a variable can have multiple different values. Use If statements for testing the boolean value of other conditional logic.
