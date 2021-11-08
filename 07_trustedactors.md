### 160. Trusted actors:

Ideally there should be no trusted actors while interacting with smart contracts.

However, in guarded launch scenarios, the goal is to start with trusted actors and then progressively decentralise towards automated governance by community/DAO.

For the trusted phase, all the trusted actors, their roles and capabilities should be clearly specified, implemented accordingly and documented for user information and examination.

### 161. Privileged roles and EOAs:

Trusted actors who have privileged roles with capabilities to deploy contracts, change critical parameters, pause/unpause system, trigger emergency shutdown, withdraw/transfer/drain funds and allow/deny other actors should be addresses controlled by multiple, independent, mutually distrusting entities.

They should not be controlled by private keys of EOAs but with Multisigs with a high threshold (e.g. 5-of-7, 9-of-11) and eventually by a DAO of token holders.

EOA has a single point of failure.

### 162. Two-step change of privileged roles:

When privileged roles are being changed, it is recommended to follow a two-step approach: 1. The current privileged role proposes a new address for the change
2. The newly proposed address then claims the privileged role in a separate transaction

This two-step change allows accidental proposals to be corrected instead of leaving the system operationally with no/malicious privileged role.

For e.g., in a single-step change, if the current admin accidentally changes the new admin to a zero-address or an incorrect address (where the private keys are not available), the system is left without an operational admin and will have to be redeployed.

### 163. Time-delayed change of critical parameters:

When critical parameters of systems need to be changed, it is required to broadcast the change via event emission and recommended to enforce the changes after a time-delay.

This is to allow system users to be aware of such critical changes and give them an opportunity to exit or adjust their engagement with the system accordingly.

For e.g. reducing the rewards or increasing the fees in a system might not be acceptable to some users who may wish to withdraw their funds and exit.
