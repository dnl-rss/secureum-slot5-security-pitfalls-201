# Function Security

### 138. Function parameters:

**BEST PRACTICE**: Ensure *input validation* for all function parameters, especially if the visibility is `external` or `public` where (untrusted) users can control values.

**WARNING**: This is especially required for `address` parameters where incorrect or zero addresses can cause vulnerabilities or unexpected behavior.

### 139. Function arguments:

**BEST PRACTICE**: Ensure that the *arguments to function calls* at the caller sites are the correct ones, and in the right order, as expected by the *function definition*.

### 140. Function visibility:

**BEST PRACTICE**: Ensure that the *strictest visibility* is used for the required functionality.

**WARNING**: An accidental `external` or `public` visibility will allow (untrusted) users to invoke functionality that is supposed to be restricted to `internal`.

### 141. Function modifiers:

**BEST PRACTICE**: Ensure that the right set of *function modifiers* are used (in the correct order) so that the expected *access control* or *validation* is correctly enforced.

### 142. Function return values:

**BEST PRACTICE**: Ensure that the appropriate *return value(s)* are returned from functions and *checked without ignoring* at function call sites
- `Error` conditions should be caught and handled appropriately.

### 143. Function invocation timeliness:

**NOTE**: `external` or `public` functions may be *called at any time* (or never).

**WARNING**: It is **not safe** to assume functions will *only be called at specific system phases* (e.g. after initialization, when unpaused, during liquidation). The reason for this can be accidental or malicious.

**BEST PRACTICE**: Function implementation should be *robust* enough to:
- track system state transitions
- determine meaningful states for invocations
- withstand arbitrary calls

e.g. *initialization functions* (used with upgradeable contracts that cannot use `constructor`) are meant to be *called atomically along with contract deployment* to prevent anyone else from initializing with arbitrary values.

### 144. Function invocation repetitiveness:

**NOTE**: `external` or `public` functions may be *called any number of times*.

**WARNING**: It is **not safe** to assume functions will *be called only once*, or a *specific number of times*.

**BEST PRACTICE**: Function implementation should be *robust* enough to track, prevent, ignore, or account for *arbitrarily repetitive invocations*.

e.g. *initialization functions* (used with upgradeable contracts that cannot use `constructor`) are meant to be *called only once*.

### 145. Function invocation order:  

**NOTE**: `external` or `public` functions may be *called in any order* (with respect to other defined functions).

**WARNING**: It is **not safe** to assume functions will only be called in a *specific order*.

e.g. *initialization functions* (used with upgradeable contracts that cannot use `constructor`) are meant to be *called before other system functions* can be called.

### 146. Function invocation arguments:

**NOTE**: `external` and `public` functions may be called with *any possible arguments*.

**WARNING**: Without *complete and proper input validation*, functions **cannot be assumed** to *comply with assumptions* made about them in the code.

**BEST PRACTICE**: Implement *input validation* on function parameters, including:
- zero address checks
- bound checks
- threshold checks

### 147. Conditionals:

**BEST PRACTICE**: Ensure that in *conditional expressions* (e.g. `if` statements), the *correct variables are being checked* and the *correct operators are being used* to combine them.

e.g. using `||` instead of `&&` is a common error.
