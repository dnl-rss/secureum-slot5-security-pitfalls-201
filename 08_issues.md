### 164. Explicit over Implicit:

While Solidity has progressively adopted explicit declarations of intent for e.g. with function visibility and variable storage, it is recommended to do the same at the application level where all requirements should be explicitly validated (e.g. input parameters) and assumptions should be documented and checked.

Implicit requirements and assumptions should be flagged as dangerous.

### 165. Configuration issues:

Misconfiguration of system components such contracts, parameters, addresses and permissions may lead to security issues.

### 166. Initialization issues:

Lack of initialization, initializing with incorrect values or allowing untrusted actors to initialize system parameters may lead to security issues.

### 167. Cleanup issues:

Missing to clean up old state or cleaning up incorrectly/insufficiently will lead to reuse of stale state which may lead to security issues.

### 168. Data processing issues:

Processing data incorrectly will cause unexpected behavior which may lead to security issues.

### 169. Data validation issues:

Missing validation of data or incorrectly/insufficiently validating data, especially tainted data from untrusted users, will cause untrustworthy system behavior which may lead to security issues.

### 170. Numerical issues:

Incorrect numerical computation will cause unexpected behavior which may lead to security issues.

### 171. Accounting issues:

Incorrect or insufficient tracking or accounting of business logic related aspects such as states, phases, permissions, roles, funds (deposits/withdrawals) and tokens (mints/burns/transfers) may lead to security issues.

### 172. Access control issues:

Incorrect or insufficient access control or authorization related to system actors, roles, assets and permissions may lead to security issues.

### 173. Auditing/logging issues:

Incorrect or insufficient emission of events will impact off-chain monitoring and incident response capabilities which may lead to security issues.

### 174. Cryptography issues:

Incorrect or insufficient cryptography especially related to on-chain signature verification or off-chain key management will impact access control and may lead to security issues.

### 175. Error-reporting issues:

Incorrect or insufficient detecting, reporting and handling of error conditions will cause exceptional behavior to go unnoticed which may lead to security issues.

### 176. Denial-of-Service (DoS) issues:

Preventing other users from successfully accessing system services by modifying system parameters or state causes denial-of-service issues which affects the availability of the system. This may also manifest as security issues if users are not able to access their funds locked in the system.

### 177. Timing issues:

Incorrect assumptions on timing of user actions, system state transitions or blockchain state/blocks/transactions may lead to security issues.

### 178. Ordering issues:

Incorrect assumptions on ordering of user actions or system state transitions may lead to security issues.

e.g.  a user may accidentally/maliciously call a finalization function even before the initialization function if the system allows.

### 179. Undefined behavior issues:

Any behavior that is undefined in the specification but is allowed in the implementation will result in unexpected outcomes which may lead to security issues.

### 180. External interaction issues:

Interacting with external components (e.g. tokens, contracts, oracles) forces system to trust or make assumptions on their correctness/availability requiring validation of their existence and outputs without which may lead to security issues.

### 181. Trust issues:

Incorrect or Insufficient trust assumption about/among system actors and external entities will lead to privilege escalation/abuse which may lead to security issues.

### 182. Gas issues:

Incorrect assumptions about gas requirements especially for loops or external calls will lead to out-of-gas exceptions which may lead to security issues such as failed transfers or locked funds.

### 183. Dependency issues:

Dependencies on external actors or software (imports, contracts, libraries, tokens etc.) will lead to trust/availability/correctness assumptions which if/when broken may lead to security issues.

### 184. Constant issues:

Incorrect assumptions about system actors, entities or parameters being constant may lead to security issues if/when such factors change unexpectedly.

### 185. Freshness issues:

Incorrect assumptions about the status of or data from system actors or entities being fresh (i.e. not stale), because of lack of updation or availability, may lead to security issues if/when such factors have been updated. For e.g., getting a stale price from an Oracle.

### 186. Scarcity issues:

Incorrect assumptions about the scarcity of tokens/funds available to any system actor will lead to unexpected outcomes which may lead to security issues. For e.g., flash loans.

### 187. Incentive issues:

Incorrect assumptions about the incentives of system/external actors to perform or not perform certain actions will lead to unexpected behavior being triggered or expected behavior not being triggered, both of which may lead to security issues.

e.g. incentive to liquidate positions, lack of incentive to DoS or grief system.

### 188. Clarity issues:

Lack of clarity in system specification, documentation, implementation or UI/UX will lead to incorrect expectations/outcome which may lead to security issues.

### 189. Privacy issues:

Data and transactions on the Ethereum blockchain are not private. Anyone can observe contract state and track transactions (both included in a block and pending in the mempool).

Incorrect assumptions about privacy aspects of data or transactions can be abused which may lead to security issues.

### 190. Cloning issues:

Copy-pasting code from other libraries, contracts or even different parts of the same contract may result in incorrect code semantics for the context being copied to, copy over any vulnerabilities or miss any security fixes applied to the original code.

All these may lead to security issues.

### 191. Business logic issues:

Incorrect or insufficient assumptions about the higher-order business logic being implemented in the application will lead to differences in expected and actual behavior, which may result in security issues.
