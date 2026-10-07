# Python

## Style and comments
- Follow PEP 8 for formatting, naming, imports, and line structure. Project conventions win only where consistent with PEP 8.
- Prefer self-explanatory code. If the code is clear, write zero comments.
- No comments that restate adjacent code.
- No chain-of-thought references or AI-session notes in comments.
- Necessary comments: at most 1 line and 7 words.

## Code structure
Organize code by role. Follow the repo's existing names; otherwise choose names where each file's role is obvious from its name and module docstring. Match neighboring files' structure and conventions.

### Roles (each in its own module or package)
- Constants: shared constants and configuration defaults.
- Models: data structures only (dataclasses, pydantic models, enums). No I/O, no orchestration.
- Core logic: classes that do the work, one responsibility each.
- Shared helpers: small stateless utilities used by more than one module.
- Entrypoint: thin wiring only. Logic lives in `main()` behind `if __name__ == '__main__':`. Importing any module has no side effects.

### Modules
- Group related classes and functions in one module; a module never mixes roles.
- Start every module with a docstring stating its role and contents.
- Dependencies point one way: entrypoint -> core logic -> models, helpers, constants. Models and constants import nothing else from the project.
- Import modules, not names, via full package paths (`constants.MAX_RETRIES`, `text_utils.slugify(...)`). No relative imports.

### Classes and functions
- Classes model domain concepts. Stateless logic is a module-level function, not a class or `staticmethod`. `classmethod` only for named constructors.
- `@property` only for cheap, trivial computed attributes. No trivial getters/setters; use public attributes.
- Keep functions small and focused; reconsider past about 40 lines.
- A helper used by one module is a module-level function with a leading underscore. Do not nest functions to hide them.

### Constants
- `CAPS_WITH_UNDER`. Check the constants module before adding one. Shared constants live there; a single-module constant sits at that module's top with a leading underscore. No inline magic numbers or strings.
- No mutable global state. Constant collections are immutable (tuple, frozenset, MappingProxyType).

### No duplication
- Before writing a helper, search the repo by name and by behavior; reuse what exists.
- If two modules need the same helper, move it to shared helpers and import it from both. Never copy a helper.
- If you find duplicated helpers or scattered constants in code you touch, consolidate them and say so in your summary.
