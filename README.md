# add-remove-liqidity
 
The provided Solidity code implements a contract called `UniswapV2AddLiquidity` which allows users to add and remove liquidity from a Uniswap V2 pair. Here's an explanation of the code:

- The contract starts with the SPDX-License-Identifier to specify the license under which the code is released.

- The contract defines several private constant addresses:
  - `FACTORY`: Represents the address of the Uniswap V2 Factory contract.
  - `ROUTER`: Represents the address of the Uniswap V2 Router contract.
  - `WETH`: Represents the address of the Wrapped Ether (WETH) token.
  - `USDT`: Represents the address of the Tether (USDT) token.

- The `addLiquidity` function allows users to add liquidity to a Uniswap V2 pair. It takes the addresses of two tokens (`_tokenA` and `_tokenB`), as well as the desired amounts of each token (`_amountA` and `_amountB`). The function transfers the specified amounts of tokens from the user to the contract using the `safeTransferFrom` function. It then approves the Router contract to spend the transferred tokens using the `safeApprove` function. Finally, it calls the `addLiquidity` function of the Router contract to add liquidity to the pair. The resulting amounts of tokens and liquidity tokens are returned.

- The `removeLiquidity` function enables users to remove liquidity from a Uniswap V2 pair. It takes the addresses of two tokens (`_tokenA` and `_tokenB`). The function retrieves the pair address using the Factory contract and calculates the amount of liquidity tokens held by the contract. It approves the Router contract to spend the liquidity tokens using the `safeApprove` function and then calls the `removeLiquidity` function of the Router contract to remove liquidity from the pair. The resulting amounts of tokens are returned.

- The contract includes two helper functions: `safeTransferFrom` and `safeApprove`. These functions handle the `transferFrom` and `approve` interactions with ERC-20 tokens. They check if the corresponding functions return a boolean value or if the return data is empty to ensure the success of the transfer or approval.

- Additionally, the contract includes several interface declarations for the Uniswap V2 Router, Factory, and ERC-20 tokens. These interfaces define the required functions and their signatures to interact with the respective contracts.

This contract provides a convenient way for users to add and remove liquidity from Uniswap V2 pairs, facilitating the liquidity provision process within the Uniswap decentralized exchange protocol.