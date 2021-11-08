### 158. ETH Handling:

Contracts that accept/manage/transfer ETH should ensure that functions handling ETH are using msg.value appropriately, logic that depends on ETH value accounts for less/more ETH sent, logic that depends on contract ETH balance accounts for the different direct/indirect (e.g. coinbase transaction, selfdestruct recipient) ways of receiving ETH and transfers are reentrancy safe.

Functions handling ETH should be checked extra carefully for access control, input validation and error handling.

### 159. Token Handling:

Contracts that accept/manage/transfer ERC tokens should ensure that functions handling tokens account for different types of ERC tokens (e.g. ERC20 vs ERC777), deflationary/inflationary tokens, rebasing tokens and trusted/external tokens.

Functions handling tokens should be checked extra carefully for access control, input validation and error handling.
