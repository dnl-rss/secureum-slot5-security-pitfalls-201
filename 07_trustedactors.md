### 160. Trusted actors:

**NOTE**: Ideally there should be *no trusted actors* while interacting with smart contracts.

**CAVEAT**: However, in *guarded launch scenarios*, the goal is to *start with trusted actors*, and then *progressively decentralize* towards automated governance by community/DAO.

**BEST PRACTICE**: Ensure that all the *trusted actors* have *clearly specified roles and capabilities*, which are *implemented accordingly* and *documented for user examination*.

### 161. Privileged roles and EOAs:

**BEST PRACTICE**: *Trusted actors* who have privileged roles *should be addresses controlled by multiple, independent, mutually distrusting entities*.

This should be implemented for privileged roles with capabilities to:
- deploy contracts
- change critical parameters
- pause/unpause system
- trigger emergency shutdown
- withdraw/transfer/drain funds
- allow/deny other actors

**WARNING**: Addresses of trusted actors should **not be controlled** by *EOAs*, which is a single point of failure.

**BEST PRACTICE**: Ensure that address of trusted actors are controlled by *Multisigs* with a high threshold of member signatures (e.g. 5-of-7, 9-of-11), and eventually by a *DAO* of token holders.

### 162. Two-step change of privileged roles:

**BEST PRACTICE**: Follow a *two step process* to change privileged roles:
1. The current privileged role *proposes a new address* for the change
2. The newly proposed address then *claims the privileged role*, in a separate transaction

**NOTE**: This two-step change allows *accidental proposals to be corrected*, instead of leaving the system with a malicious or locked privileged role.

e.g. in a single-step change, if the current admin accidentally changes the new admin to a zero-address or an incorrect address (where the private keys are not available), the system is left without an operational admin and will have to be redeployed.

### 163. Time-delayed change of critical parameters:

**BEST PRACTICE**: Whenever critical parameters of systems must be changed:
- broadcast the change via event emission
- enforce the changes after a time-delay

**NOTE**: These practices allow system users to be aware of critical changes and give them an opportunity to exit or adjust their engagement with the system accordingly.

e.g. reducing rewards or increasing fees in a system might not be acceptable to some users, who may wish to withdraw their funds and exit before the change is implemented.
