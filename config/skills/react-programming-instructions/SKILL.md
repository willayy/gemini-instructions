---
name: react-programming-instructions
description: Contains React and TypeScript coding rules that must be followed when writing, editing, reviewing, or refactoring React code.
---

# React Programming Instructions

This styleguide defines rules for writing React and TypeScript code, utilizing MVVM architecture, dependency injection, composition, and colocation.

**Rules:**
- **MVVM Architecture:**
  - **Model:** Pure business logic and domain state are placed in the Model.
  - **View-Model (VM):** UI state and dynamics are handled exclusively by the View-Model.
  - **View:** The View only handles visual representation. The View should only use view components.
- **View-Model Declaration and Dependency Injection:** The View-Model function must be declared in the same file as the View function and injected into the View via dependency injection.
- **Composition over Redeclaration:** Rely on `props` and `children` in components to promote composition over redeclaration.
- **Colocation:** Code that is used together is located together.
- **Shared Code Organization:** Components or logic used in multiple places must be placed in a root `.../src/` directory:
  - `.../src/utils/`: For reusable generalist logic.
  - `.../src/lib/`: For integration with, or other kinds of use of, other software.
  - `.../src/components/`: For reusable shared UI components.
  - `.../src/hooks/`: For reusable shared hooks.
