### 154. Comments:

**BEST PRACTICE**: Ensure that the code is *well commented*, both with *NatSpec* and *inline comments*, for better readability and maintainability.
- Comments should accurately reflect what the corresponding code does.
- Stale comments should be removed
- Discrepancies between code and comments should be addressed
- Any TODO’s indicated by comments should be addressed
- Commented code should be removed

### 155. Tests:

**NOTE**: *Tests* indicate that the *system implementation* has been *validated against the specification*.

**BEST PRACTICE**: Perform unit tests, functional tests, and integration tests across the entire codebase.
- Any code or parameterisation used specifically for testing should be removed from production code.

### 156. Unused constructs:

**BEST PRACTICE**: Unused imports, inherited contracts, functions, parameters, variables, modifiers, events or return values *should be removed* (or used appropriately) after careful evaluation.

**NOTE**: Removing unused constructs not only reduces gas costs, but also improves readability and maintainability.

### 157. Redundant constructs:

**BEST PRACTICE**: Redundant code and comments can be confusing and *should be removed* (or changed appropriately) after careful evaluation.

**NOTE**: Removing redundant constructs not only reduces gas costs, but also improves readability and maintainability.
