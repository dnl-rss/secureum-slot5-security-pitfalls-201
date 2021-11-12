# Access Control

## Access Control Specification and Implementation

### 148. Access control specification:

**BEST PRACTICE**: Ensure that the *access control privileges* and *trust assumptions* of various system actors are accurately *specified in great detail*

**NOTE**: This specification is required to evaluate if they are correctly implemented and enforced across different contracts, functions, and system transitions/flows.

### 149. Access control implementation:

**BEST PRACTICE**: Ensure that the *specified access control* is *implemented uniformly* across all the subjects (actors) seeking access and objects (variables, functions) being accessed.

**WARNING**: There must be **no paths/flows where the access control is missing** or may be side-stepped.

## Access Control Modifiers

**NOTE**: Access control is typically enforced on functions using *modifiers that check if specific addresses/roles are calling these functions*.

**NOTE**: A system can have *multiple roles* with *different privileges*.

### 150. Missing modifiers:

**BEST PRACTICE**: Ensure that *access control modifiers* are present on all relevant functions which require that specific access control.

### 151. Incorrectly implemented modifiers:

**BEST PRACTICE**: Ensure that modifiers *implement the expected checks* on the correct roles/addresses with the right composition

e.g. incorrect use of `||` instead of `&&` is a common vulnerability while composing access checks.

### 152. Incorrectly used modifiers:

**BEST PRACTICE**: Ensure that *correct modifiers* are used on functions requiring specific access control enforced by that modifier.

## Access Control Changes

### 153. Access control changes:

**BEST PRACTICE**: Ensure that *changes to access control* (e.g. change of ownership to new addresses) are handled with *extra security*, so that such transitions happen smoothly without contracts getting locked or compromised due to use of *incorrect credentials*.
