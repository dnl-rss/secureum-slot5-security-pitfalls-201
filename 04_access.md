### 148. Access control specification:

Ensure that the various system actors, their access control privileges and trust assumptions are accurately specified in great detail so that they are correctly implemented and enforced across different contracts, functions and system transitions/flows.

### 149. Access control implementation:

Ensure that the specified access control is implemented uniformly across all the subjects (actors) seeking access and objects (variables, functions) being accessed so that there are no paths/flows where the access control is missing or may be side-stepped.

### 150. Missing modifiers:

Access control is typically enforced on functions using modifiers that check if specific addresses/roles are calling these functions.

Ensure that such modifiers are present on all relevant functions which require that specific access control.

### 151. Incorrectly implemented modifiers:

Access control is typically enforced on functions using modifiers that check if specific addresses/roles are calling these functions.

A system can have multiple roles with different privileges. Ensure that modifiers are implementing the expected checks on the correct roles/addresses with the right composition

e.g. incorrect use of `||` instead of `&&` is a common vulnerability while composing access checks.

### 152. Incorrectly used modifiers:

Access control is typically enforced on functions using modifiers that check if specific addresses/roles are calling these functions.

A system can have multiple roles with different privileges.

Ensure that correct modifiers are used on functions requiring specific access control enforced by that modifier.

### 153. Access control changes:

Ensure that changes to access control (e.g. change of ownership to new addresses) are handled with extra security so that such transitions happen smoothly without contracts getting locked out or compromised due to use of incorrect credentials.
