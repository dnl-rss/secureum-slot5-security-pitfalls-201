### 158. ETH Handling:

**BEST PRACTICE**: Ensure that functions *handling ETH* use `msg.value` appropriately:
- logic that depends on `value` accounts for less/more ETH sent
- logic that depends on contract `balance` accounts for the different direct/indirect ways of receiving ETH (e.g. coinbase transaction, selfdestruct recipient)
- all transfers are reentrancy safe

**BEST PRACTICE**: Ensure that functions handling ETH have appropriate *access control, input validation, and error handling*.

### 159. Token Handling:

**BEST PRACTICE**: Ensure that functions *handling ERC tokens* account for *different types of ERC tokens*:
- ERC20 vs ERC777
- Deflationary/inflationary tokens
- Rebasing tokens
- Trusted/external tokens

**BEST PRACTICE**: Ensure that functions handling ERC tokens have appropriate *access control, input validation, and error handling*.
