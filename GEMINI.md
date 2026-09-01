# General Instructions
- I am fluent in English and Swedish.
- My ethnicity and nationality is Swedish.
- I am born on the 8th of November 2001.
- Ask follow-up questions, before answering, when the question, answer or any other form of input from the user is ambiguous.
- Be critical of the sources you use.
- Use a neutral tone.
- Only use metaphors and analogies when explicitly asked.
- Use the Celsius temperature scale.
- Explain used Jargon in parentheses.
- Use the metric system.
- Write short and direct answers.
- For testing new features, testing behavior, reproducing errors or diagnosing bugs prefer using inline python code through the terminal
- Any extra programs written by the agent to complete a task should be placed in the scratch dir (`/Users/williamnorland/.gemini/antigravity/scratch` or `/Users/williamnorland/.gemini/antigravity-ide/scratch`) nowhere else.
- Always ask if code being worked on should be run or not.

# Git Rules
This section defines rules for creating Git commits and writing commit messages.

## Definitions
- **Broken:** Any segment of code that is producing unintended, unexpected (that is, it is not a documented and accepted unintended behavior) behavior.
- **Software Object (SO):** A function, method, class, global constant, global variable, configuration file, or documentation file.

## Prefixes
When to use what prefix:
- `NEW:` Used when a new SO is added.
- `FIX:` Used when any change on an existing SO has the purpose of fixing something that is broken.
- `CHANGE:` Used when any change on an existing SO does NOT have the purpose of fixing something that is broken.

## Constraints
- Exactly one commit per individual SO change. Never group changes to multiple SOs into a single commit.

## Format
```text
<Prefix> <description>

[optional body]
```

# Python Style Guide

This styleguide aims to be a complement to the PEP styleguides & unwritten idiomatic Python rules supplementeting any gaps that they leave and as such they have precedence over any rule defined in this style guide.

**Rules:**
- Normally named functions means public functions.
- _ means module private functions.
- Inner helper functions should walways be written like a public functions since its visibility is limited by default.
- Each file (module) should only do one thing meaning it should generally only expose 1 public function. The only time it shouldnt is if there is very similar functionality that cant be included via paramaters.
- No code, except match/case statements, may nest deeper than one level from the root level of a function, file or class.
- Use Match/Case statements for equality checks where a variable can have multiple different values. Use If statements for testing the boolean value of other conditional logic.
- Function names should always be written as `<verb>_<preposition>,...,<preposition>_<noun>`.
- File names (modules) and classes should have their responsibility documented using a header doc string that has the format:
```py
"""Responsible for handling XYZ within ABC..."""
...
```

**Design recommendations**
- All generic logic (functions, classes, files) that is so general that it cant be associated with JUST a single functionality is regarded as something that should be placed in a utils.py file. For example filtering, sorting, distance calculations, mapping etc. A lot of these functions are already available from the Python standard library, which should always be consulted _before_ implementing such generic functions.

**Examples of illegal nesting:**
```py
for i in range(a):
    for j in range (b):
        # Already illegal
        for k in range(c):
            # Very illegal...
            ...
```
