### 164. Explicit over Implicit:

**NOTE**: Solidity has progressively adopted explicit declarations of intent, for example with function visibility and variable storage.

**BEST PRACTICE**: Ensure that all requirements are explicitly validated (e.g. input parameters) and that assumptions are documented and checked at the application level.

**BEST PRACTICE**: Implicit requirements and assumptions should be flagged as dangerous.

# Common Issues

The following practices may lead to security issues:

### 165. Configuration issues:

Misconfiguration of system components such as:
- contracts
- parameters
- addresses
- permissions

### 166. Initialization issues:

- lack of initialization
- initializing with incorrect values
- allowing untrusted actors to initialize system parameters

### 167. Cleanup issues:

These may lead to *reuse of stale state data*
- leaving old state data
- cleaning up incorrectly/insufficiently

### 168. Data processing issues:

*Processing data incorrectly* will cause unexpected behavior.

### 169. Data validation issues:

Validation issues may lead to untrustworthy system behavior:
- missing validation of data
- incorrectly/insufficiently validating data, especially tainted data from untrusted users

### 170. Numerical issues:

Incorrect numerical computation will cause unexpected behavior.

### 171. Accounting issues:

Incorrect or insufficient tracking or accounting of business logic related aspects such as:
- states
- phases
- permissions
- roles
- funds (deposits/withdrawals)
- tokens (mints/burns/transfers)

Leads to issues.

### 172. Access control issues:

Incorrect or insufficient access control or authorization related to:
- system actors
- roles
- assets
- permissions

Leads to issues.

### 173. Auditing/logging issues:

Incorrect or insufficient emission of events will impact off-chain monitoring and incident response capabilities.

### 174. Cryptography issues:

Incorrect or insufficient cryptography especially related to:
- on-chain signature verification
- off-chain key management

Will impact access control.

### 175. Error-reporting issues:

Incorrect or insufficient detecting, reporting, and handling of *error conditions* will cause *exceptional behavior to go unnoticed*.

### 176. Denial-of-Service (DoS) issues:

Denial-of-service issues affect the *availability* of a system:
- users may be prevented from accessing system services by modifying key system parameters or state
- may also manifest as security issues if users are not able to access their funds locked in the system

### 177. Timing issues:

Incorrect assumptions on timing of user actions, system state transitions, or blockchain state/blocks/transactions may lead to security issues.

### 178. Ordering issues:

Incorrect assumptions on *ordering* of *user actions* or *system state transitions* may lead to security issues.

e.g. a user may accidentally/maliciously call a finalization function even before the initialization function if the system allows.

### 179. Undefined behavior issues:

Behavior that is *undefined in the specification* but is *allowed in the implementation* will result in unexpected outcomes.

### 180. External interaction issues:

Interaction with *external components* forces the system to *trust* or make assumptions on their correctness/availability, requiring validation of their existence and outputs.

e.g. interaction with tokens, contracts, oracles

### 181. Trust issues:

Incorrect or Insufficient *trust assumptions* about system actors and external entities will lead to *privilege escalation or abuse*.

### 182. Gas issues:

Incorrect assumptions about *gas requirements*, especially for-loops or external calls, will lead to *out-of-gas exceptions* resulting in failed transfers or locked funds.

### 183. Dependency issues:

*Dependencies on external actors or software* requires assumptions on their *trustworthiness, availability, and correctness*.

e.g. imports, contracts, libraries, tokens etc.

### 184. Constant issues:

Incorrect assumptions about system actors, entities, or parameters being `constant` may lead to security issues if such factors change unexpectedly.

### 185. Freshness issues:

Incorrect assumptions about the status of, or data from, system actors being "fresh" (not stale), because of lack of updating or availability, may lead to security issues if/when such factors have been updated.

e.g. getting a stale price from an Oracle

### 186. Scarcity issues:

Incorrect assumptions about the *scarcity of tokens/funds* available to any system actor will lead to unexpected outcomes.

e.g. flash loans

### 187. Incentive issues:

Incorrect assumptions about the *incentives* encouraging external actors to perform, or not perform, certain actions will lead to unexpected behavior being triggered or expected behavior not being triggered.

e.g. incentive to liquidate positions, lack of incentive to DoS or grief system.

### 188. Clarity issues:

*Lack of clarity* in system specification, documentation, implementation or UI/UX will lead to incorrect expectations/outcomes.

### 189. Privacy issues:

Incorrect assumptions about *privacy aspects* of data or transactions can be abused:
- Data stored on the Ethereum blockchain are not private, even when marked so
- Anyone can observe contract state and track transactions (both included in a block and pending in the mempool)

### 190. Cloning issues:

Copy-pasting code from other libraries, contracts, or even different parts of the same contract may result in:
- incorrect code semantics applied to the context being copied to
- copying over any vulnerabilities
- missing any security fixes applied to the original code

### 191. Business logic issues:

Incorrect or insufficient assumptions about the *higher-order business logic* being implemented in the application will lead to differences in expected and actual behavior.
