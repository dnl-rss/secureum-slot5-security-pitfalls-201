# Guarded Launches

Guarded launches with centralized administrative controls and restricted user permissions are recommended to vet newly deployed protocols, while transitioning to more decentralized and permissionless designs. This model may reduce impact due to initial vulnerabilities and exploits.

[ref](https://medium.com/electric-capital/derisking-defi-guarded-launches-2600ce730e0a#:~:text=Guarded%20Launches:%20Protecting%20Users%20with%20Limits&text=A%20new%20contract%20is%20deployed,product%20in%20a%20limited%20scope)

### 128. asset limits:

Limit the *total asset value* managed by a system initially, and gradually increase it.

### 129. asset types:

Limit the *types of assets* that can be used in the protocol initially, and gradually expand to other assets.

### 130. user limits:

Limit the *total number of users* that can interact with a system initially, and gradually increase it.

Initial users may also be *whitelisted* to limit to trusted actors before opening the system to everyone.

### 131. usage limits:

Enforce transaction *size limits, daily volume limits, per-account limits, or rate-limiting transactions*.

### 132. composability limits:

Restrict the *composability* of the system to interface only with *whitelisted trusted contracts*, before expanding to *arbitrary external contracts*.

### 133. escrows:

*Escrow high value transactions/operations* with time locks and a governance capability to nullify or revert malicious transactions.

### 134. circuit breakers:

Implement *pause/unpause* capabilities for use in extreme scenarios.

### 135. emergency shutdown:

Implement *emergency shutdown* capabilities, and allow users to reclaim assets.
