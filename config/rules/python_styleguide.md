# Python Style Guide

**Intention**
This styleguide aims to be a complement to the PEP styleguides & unwritten idiomatic Python rules supplementeting any gaps that they leave and as such they have precedence over any rule defined in this style guide.

**Rules:**
- Normally named functions means public functions.
- _ means module private functions.
- Inner helper functions should walways be written like a public functions since its visibility is limited by default.
- Each file (module) should only do one thing meaning it should generally only expose 1 public function. The only time it shouldnt is if there is very similar functionality that cant be included via paramaters.
- No code, except match/case statements, may nest deeper than one level from the root level of a function, file or class.
- Use Match/Case statements for equality checks where a variable can have multiple different values. Use If statements for testing the boolean value of other conditional logic.
- Function names should always be written as `<verb>_<preposition>,...,<preposition>_<noun>`.
- File names (modules) and classes should have their responsibility documented using a header doc string that has the format.
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
