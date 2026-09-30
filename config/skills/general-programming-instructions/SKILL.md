---
name: general-programming-instructions
description: Contains programming rules that must be followed when writing, reviewing, or refactoring code in any programming language.
---

# General Programming Instructions
These rules form the basis of, and are implicitly included in, all other language-specific style and design guides, but language-specific style and design guides take precedence when there is a conflict.

- Separation of concerns: A piece of code should ever only do one thing.
- SRP adherence: The Single Responsibility Principle should be followed in all scopes, be it functions, classes, files, or packages. A piece of code should only have one reason to change.
- Use Encapsulation: Encapsulation should always be used to present a comprehensive interface for clients and hide complexity.
- LOD adherence: Adhere to the Law of Demeter (the principle of least knowledge, stating that an object or component should only interact with its immediate dependencies).
- ISP adherence: Adhere to the Interface Segregation Principle, clients should not be forced to depend on interfaces or methods they do not use.
- DIP adherence: Adhere to the Dependency Inversion Principle, high-level modules should not depend on low-level modules; both should depend on abstractions.
- Open source and standard library reuse: Never implement functionality that you can get from an open source package or a standard library.
- Function naming: Functions should always follow a verb-(optional) preposition-noun structure (e.g. send_emails); if a preposition can be added, it should be added (e.g. transform_to_json).
- Nested calls: Function calls should not be nested; call a function, store the return value in a variable, and then pass the variable.
- Indenting and nesting: No code, except switch statements, may nest deeper than one level from the root level of a function, file or class.
- Line limits: Lines of code should not span more than 100 characters.
- Data storage: Do not store data in code.
- Anonymous functions: Anonymous functions should never bypass the line limit, though shorter ones used for maps and predicates are acceptable.

**Examples of illegal nesting:**
```py
for i in range(a):
    for j in range (b):
        # Already illegal
        for k in range(c):
            # Very illegal...
            ...
```

**Examples of illegal nested calls:**
```py
result = process_user(fetch_account(get_user_id()))
```

**Examples of illegal anonymous functions:**
```py
users = map(lambda user: format_profile(user.id, user.attributes) if user.is_active else default_profile(user.id), dataset)
```

**Examples of Law of Demeter (LOD) violations:**
```py
city = order.get_customer().get_address().get_city()
```
