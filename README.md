# Bounty - Write a DeFi Script

## Overview of Script

Welcome to the Write a DeFi Script Bounty Challenge! This script demonstrates the integration and composability of different DeFi protocols by performing a token swap on Uniswap and then supplying the swapped tokens to Aave to start earning interest.

### Key Features:

1. **Token Swap on Uniswap**: The script swaps USDC for LINK using Uniswap.
2. **Supply to Aave**: After the swap, the script supplies the LINK tokens to Aave to earn interest.

## Diagram Illustration

Below is a diagram illustrating the sequence of steps and interactions between the protocols:

![alt text](diagram.png)

### Workflow:

1. **Initialization and Configuration**:

   - Load environment variables using `dotenv`.
   - Define constants for contract addresses and token configurations.
   - Initialize the provider and signer.
   - Create contract instances for the factory, lending pool, and swap router.

2. **Token Approval**:

   - Approve the USDC token for the swap router contract.
   - Function: `approveToken(tokenAddress, tokenABI, amount, wallet)`

3. **Get Pool Information**:

   - Retrieve the pool contract address for the USDC-LINK pair.
   - Function: `getPoolInfo(factoryContract, tokenIn, tokenOut)`

4. **Prepare Swap Parameters**:

   - Prepare the parameters required for the swap transaction.
   - Function: `prepareSwapParams(poolContract, signer, amountIn)`

5. **Execute Swap**:

   - Execute the swap transaction on the swap router contract.
   - Function: `executeSwap(swapRouter, params, signer)`

6. **Approve Lending Pool**:

   - Approve the LINK token for the lending pool contract.
   - Function: `approveLendingPool(tokenAddress, amount, wallet)`

7. **Supply to Aave**:

   - Supply the swapped LINK tokens to the Aave lending pool.
   - Function: `supplyToAave(lendingPool, amount, tokenAddress, wallet)`

8. **Main Function Execution**:
   - Call the main function with the swap amount.
   - Function: `main(swapAmount)`

## Final terminal output

![alt text](<final terminal output.png>)

## Conclusion

This script demonstrates the integration of Uniswap and Aave protocols to perform a token swap and supply the swapped tokens to earn interest. By following the steps outlined in this README, you can understand the workflow and the interactions between the different DeFi protocols.Feel free to modify the script to suit your needs and explore other DeFi protocols to enhance the functionality further.

## How to Run

1. Clone the repository:
   `git clone https://github.com/ZibrasIsmail/Bounty---Write-a-DeFi-Script`

2. Install dependencies:
   `npm install`

3. Create a .env file and add your environments variables:

   ```
   RPC_URL=your_rpc_url
   ```

   ```
   PRIVATE_KEY=your_private_key
   ```

4. Run the script:
   `node index.js`
