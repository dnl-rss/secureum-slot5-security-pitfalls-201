## Guarded Launches

Guarded launches with centralized controls and restricted permissions are recommended to vet deployed protocols, while transitioning to more decentralized and permissionless designs

[ref](https://medium.com/electric-capital/derisking-defi-guarded-launches-2600ce730e0a#:~:text=Guarded%20Launches:%20Protecting%20Users%20with%20Limits&text=A%20new%20contract%20is%20deployed,product%20in%20a%20limited%20scope.)

###128. asset limits:

Limiting the total asset value managed by a system initially upon launch and gradually increasing it over time may reduce impact due to initial vulnerabilities or exploits.

### 129. asset types:

Limiting types of assets that can be used in the protocol initially upon launch and gradually expanding to other assets over time may reduce impact due to initial vulnerabilities or exploits.

### 130. user limits:

Limiting the total number of users that can interact with a system initially upon launch and gradually increasing it over time may reduce impact due to initial vulnerabilities or exploits.

Initial users may also be whitelisted to limit to trusted actors before opening the system to everyone.

### 131. usage limits:

Enforcing transaction size limits, daily volume limits, per-account limits, or rate-limiting transactions may reduce impact due to initial vulnerabilities or exploits.

### 132. composability limits:

Restricting the composability of the system to interface only with whitelisted trusted contracts before expanding to arbitrary external contracts may reduce impact due to initial vulnerabilities or exploits.

### 133. via escrows:

Escrowing high value transactions/operations with time locks and a governance capability to nullify or revert transactions may reduce impact due to initial vulnerabilities or exploits.

### 134. circuit breakers:

Implementing capabilities to pause/unpause a system in extreme scenarios may reduce impact due to initial vulnerabilities or exploits.

### 135. emergency shutdown:

Implement capabilities that allow governance to shutdown new activity in the system and allow users to reclaim assets may reduce impact due to initial vulnerabilities or exploits.
