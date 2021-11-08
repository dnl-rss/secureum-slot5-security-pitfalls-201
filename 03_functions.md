### 138. Function parameters:

Ensure input validation for all function parameters especially if the visibility is external/public where (untrusted) users can control values.

This is especially required for address parameters where maliciously/accidentally used incorrect/zero addresses can cause vulnerabilities or unexpected behavior.

### 139. Function arguments:

Ensure that the arguments to function calls at the caller sites are the correct ones and in the right order as expected by the function definition.

### 140. Function visibility:

Ensure that the strictest visibility is used for the required functionality.

An accidental external/public visibility will allow (untrusted) users to invoke functionality that is supposed to be restricted internally.

### 141. Function modifiers:

Ensure that the right set of function modifiers are used (in the correct order) for the specific functions so that the expected access control or validation is correctly enforced.

### 142. Function return values:

Ensure that the appropriate return value(s) are returned from functions and checked without ignoring at function call sites, so that error conditions are caught and handled appropriately.

### 143. Function invocation timeliness:

Externally accessible functions (external/public visibility) may be called at any time (or never).

It is not safe to assume they will only be called at specific system phases (e.g. after initialization, when unpaused, during liquidation) that is meaningful to the system design.

The reason for this can be accidental or malicious.

Function implementation should be robust enough to track system state transitions, determine meaningful states for invocations and withstand arbitrary calls.

For e.g., initialization functions (used with upgradeable contracts that cannot use constructors) are meant to be called atomically along with contract deployment to prevent anyone else from initializing with arbitrary values.

### 144. Function invocation repetitiveness:

Externally accessible functions (external/public visibility) may be called any number of times. It is not safe to assume they will only be called only once or a specific number of times that is meaningful to the system design.

Function implementation should be robust enough to track, prevent, ignore or account for arbitrarily repetitive invocations.

For e.g., initialization functions (used with upgradeable contracts that cannot use constructors) are meant to be called only once.

### 145. Function invocation order:  

Externally accessible functions (external/public visibility) may be called in any order (with respect to other defined functions).

It is not safe to assume they will only be called in the specific order that makes sense to the system design or is implicitly assumed in the code.

For e.g., initialization functions (used with upgradeable contracts that cannot use constructors) are meant to be called before other system functions can be called.

### 146. Function invocation arguments:

Externally accessible functions (external/public visibility) may be called with any possible arguments.

Without complete and proper validation (e.g. zero address checks, bound checks, threshold checks etc.), they cannot be assumed to comply with any assumptions made about them in the code.

### 147. Conditionals:

Ensure that in conditional expressions (e.g. if statements), the correct variables are being checked and the correct operators, if any, are being used to combine them.

e.g. using `||` instead of `&&` is a common error.
