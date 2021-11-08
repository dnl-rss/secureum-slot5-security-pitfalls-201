## ERC20 Checks

The security tool [Slither](https://github.com/crytic/building-secure-contracts/blob/master/development-guidelines/token_integration.md#erc-conformity includes a utility, slither-check-erc) that reviews the conformance of a token to many related ERC standards.

```sh
// slither check example here
```

The following properties are reviewed by slither-check-erc:

### 102. ERC20 transfer and transferFrom:

`ERC20` functions `transfer()` and `transferFrom()` should return `bool`.

**WARNING**: Several faulty `ERC20` implementations do **not** return `bool` on `transfer()` and `transferFrom()`. As a result, their calls in the contract might fail.

### 103. ERC20 name, decimals, and symbol functions:

`ERC20` functions `name`, `decimals`, and `symbol` are optional and might not be present.

### 104. ERC20 decimals returns a uint8:

`ERC20` function `decimals()` should returns `uint8`.

**WARNING**: Several faulty `ERC20` implementations incorrectly return `uint256` for `decimals()`. If this is the case, ensure the value returned is below 255.

### 105. ERC20 approve race-condition:

**WARNING**: `ERC20` has a known *race condition* on `approve()`. This must be mitigated to prevent attackers from stealing tokens.

[ref](https://github.com/ethereum/EIPs/issues/20#issuecomment-263524729)

### 106. ERC777 hooks:

`ERC777` tokens have the concept of a hook function.

The hook is called before any calls to `send`, `transfer`, `operatorSend`, `mint` and `burn`.

**WARNING**: While `ERC777` hooks enable a lot of interesting use cases, care should be taken to make sure they do not make external calls because that can *lead to reentrancies*.

### 107. Token Deflation via fees:

`transfer()` and `transferFrom()` should not take a fee.

**WARNING**: Deflationary tokens can lead to unexpected behavior.

### 108. Token Inflation via interest:

Some tokens distribute interest to token holders.

Potential interest earned from the token should be taken into account.

**WARNING**: Earned interest might be trapped in the contract if not taken into account.

## Contract Composition Checks

[ref](https://github.com/crytic/building-secure-contracts/blob/master/development-guidelines/token_integration.md#contract-composition)

### 109. Token contract avoids unneeded complexity:

The token should be a simple contract; complex code requires a higher standard of review.

### 110. Token contract has only a few non–token-related functions:

Non–token-related functions increase the likelihood of an issue in the contract.

### 111. Token only has one address:

Tokens with *multiple entry points* for `balance` updates can break internal bookkeeping based on the `address`

e.g. `balances[token_address][msg.sender]` might not reflect the actual balance.

## Owner Privileges

Slither [ref](https://github.com/crytic/building-secure-contracts/blob/master/development-guidelines/token_integration.md#owner-privileges)

### 112. Token is not upgradeable:

Upgradeable contracts might change their rules over time.

### 113. Token owner has limited minting capabilities:

Malicious or compromised owners can abuse minting capabilities.

### 114. Token is not pausable:

Malicious or compromised owners can trap contracts relying on pausable tokens.

### 115. Token owner cannot blacklist the contract:

Malicious or compromised owners can trap contracts relying on tokens with a blacklist.

### 116. Token development team is known and can be held responsible for abuse:

Contracts with anonymous development teams, or that reside in legal shelters should require a higher standard of review.

## Token Scarcity

Slither [ref](https://github.com/crytic/building-secure-contracts/blob/master/development-guidelines/token_integration.md#token-scarcity)

### 117. No token user owns most of the supply:

If a few users own most of the tokens, they can influence operations based on the token's repartition.

### 118. Token total supply is sufficient:

Tokens with a low total supply can be easily manipulated.

### 119. Tokens are located in more than a few exchanges:

If all the tokens are in one exchange, a compromise of the exchange can compromise the contract relying on the token.

### 120. Token balance and Flash loans:

Users understand the associated risks of large funds or flash loans.

Contracts relying on the token balance must carefully take in consideration attackers with large funds or attacks through flash loans.

### 121. Token does not allow flash minting:

Flash minting can lead to substantial swings in the balance and the total supply, which necessitate strict and comprehensive overflow checks in the operation of the token.

## Token Checklist

[ref](https://gist.github.com/shayanb/cd495e23c7cf1a8b269f8ce7fd198538#file-token_checklist-md)

### 122. ERC1400 permissioned addresses:

Can block transfers from/to specific addresses.

### 123. ERC1400 forced transfers:

Trusted actors have the ability to transfer funds however they choose.

### 124. ERC1644 forced transfers:

Controller has the ability to steal funds.

### 125. ERC621 control of totalSupply:

totalSupply can be changed by trusted actors

### 126. ERC884 cancel and reissue:

Token implementers have the ability to cancel an address and move its tokens to a new address

### 127. ERC884 whitelisting:

Tokens can only be sent to whitelisted addresses
