# General Programming Instructions

These rules form the basis of, and are implicitly included in, all other language-specific style and design guides, but language-specific style and design guides take precedence when there is a conflict.

- **Separation of concerns:** A piece of code should ever only do one thing.
- **SRP adherence:** The Single Responsibility Principle should be followed in all scopes, be it functions, classes, files, or packages. A piece of code should only have one reason to change, where a "reason to change" refers to an actor—a single person, role, or stakeholder group that requests changes to the software.
- **Use Encapsulation:** Encapsulation should always be used to present a comprehensive interface for clients and hide complexity.
- **Composition over redeclaration:** Build complex objects and components through composition of simple, focused and reusable parts rather than redeclaring behavior.
- **Composition and inheritance:** Generally build objects through composition of simpler objects, but if behavior is widely shared then inheritance SHOULD be used instead of adding the same object field to all classes.
- **LOD adherence:** Adhere to the Law of Demeter (the principle of least knowledge, stating that an object or component should only interact with its immediate dependencies).
- **ISP adherence:** Adhere to the Interface Segregation Principle, clients should not be forced to depend on interfaces or methods they do not use.
- **DIP adherence:** Adhere to the Dependency Inversion Principle, high-level modules should not depend on low-level modules; both should depend on abstractions.
- **Open source and standard library reuse:** Never implement software or functionality that can be obtained from an open source package or the standard library.
- **Function naming:** Functions should always follow a verb-(optional) preposition-noun structure (e.g. send_emails); if a preposition can be added, it should be added (e.g. transform_to_json).
- **Nested calls:** Function calls should not be nested; call a function, store the return value in a variable, and then pass the variable.
- **Indenting and nesting:** No code, except switch statements, may nest deeper than one level from the root level of a function, file or class.
- **Line limits:** Lines of code should not span more than 100 characters.
- **Data storage:** Do not store data in code.
- **Anonymous functions:** Anonymous functions should never bypass the line limit, though shorter ones used for maps and predicates are acceptable.

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

**Examples of composition anti-patterns:**
```py
# Anti-pattern: adding a position field to all entity classes with an interface
# instead of having them inherit a shared base class
class Entity(Protocol):
    position: Position

class Player:
    def __init__(self, position: Position) -> None:
        self.position = position

class Enemy:
    def __init__(self, position: Position) -> None:
        self.position = position

# Correct: share widely used state through BaseEntity parent
class BaseEntity:
    def __init__(self, position: Position) -> None:
        self.position = position

class Player(BaseEntity):
    pass

class Enemy(BaseEntity):
    pass
```

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
