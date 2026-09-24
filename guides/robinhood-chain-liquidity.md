# How to provide liquidity on Robinhood Chain

Robinhood Chain is an Ethereum layer 2 built on Arbitrum Nitro (chain id 4663, mainnet since July 2026). Uniswap v3 and v4 run there, and a large share of the volume is in tokenized stock pools. This guide covers what is different about LP on this chain and how to do it from Tidepool.

## What is on the chain

-   **Uniswap v3 and v4** with the standard contracts. WETH9 is at 0x0Bd7D308f8E1639FAb988df18A8011f41EAcAD73.
-   **Tokenized stocks** issued as "Robinhood Token" ERC-20s (for example NVDA, TSLA) paired with USDG, the Global Dollar stablecoin.
-   **USDG** as the main quote asset. Bridges deliver USDG when you send USDC in.

## What is different from Base

-   **Ordering.** Arbitrum Nitro chains order transactions first come, first served. A priority fee changes nothing. Tidepool's speed setting is ignored here on purpose.
-   **Hook fees.** Some v4 stock pools use a hook that keeps its own cut and pays LPs nothing through the pool fee. A pool key fee of 0 can mean a dynamic fee hook (the real fee is in each swap event) or a hook with no LP fee at all. Tidepool reads swap events to show the real LP fee and hides pools that pay LPs nothing.
-   **Market hours.** Stock tokens track a market that is closed at night and on weekends. Price gaps at the open can jump a tight range. Widen ranges before the weekend or close before the open.
-   **Public RPC limits.** The public RPC refuses bursts of log queries. Tidepool routes reads through its own proxy with an archive provider.

## Step by step in Tidepool

1.  **Connect** an EVM wallet (MetaMask, Rabby, Phantom, Coinbase Wallet) on [tidepool.ag](https://tidepool.ag/).
2.  **Bridge in** through the Deposit sheet. Across moves ETH or USDC from Base; Relay moves funds from Solana. Robinhood Chain receives USDG for USDC.
3.  **Search** with the Robinhood Chain filter and sort by 24h fee to TVL. Use the Assets filter to see stock pools only or hide them.
4.  **Range.** Pick ticks on the candle chart. For stock pools, the chart shows the last traded price, which stays flat while the market is closed.
5.  **Amount.** Enter one token. Tidepool swaps the rest through the pool you are entering and mints the position. v4 mints are sized with room for a price move and capped at the amounts you entered.
6.  **Claim, close, zap out** from Portfolio at any time. Uniswap v3 claims can sell the fees to one token in the same transaction.

## Reading a Robinhood Chain pool in Tidepool

Each pool card shows fee to TVL for 24h, 7d and 30d, volume, total TVL and active TVL for the range you set. The LP fee shown is the fee LPs receive, read on chain, not the number in the pool name. If Tidepool shows no fee, the pool's hook keeps the fee and you should not LP there.

---

Source: [tidepool.ag/guides/robinhood-chain-liquidity](https://tidepool.ag/guides/robinhood-chain-liquidity). The website is the canonical version of this page.
