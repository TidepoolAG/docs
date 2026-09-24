# Cross-chain LP management

Concentrated liquidity pays the best fees in DeFi, and the best pools are not all on one chain. Meteora DLMM on Solana, Uniswap v4 on Base, tokenized stocks on Robinhood Chain. This guide explains how to hold positions on all three without three apps, three tabs and three mental models.

## The problem

Each DEX app shows only its own positions. To know what you earn in total, you add up numbers by hand. To claim fees, you visit each app. To move capital to the chain where fees are best this week, you leave for a bridge and come back. Most LPs end up staying on one chain, not because it pays best but because it is simpler.

## One portfolio

Tidepool reads your Meteora DLMM and DAMM v2 positions on Solana and your Uniswap v3 and v4 positions on Base, Robinhood Chain and Arc, and shows them in one list with the same fields: value, claimable fees, PnL, range and current price, volume and fee to TVL of the pool. Totals are per chain and overall. A performance curve is sampled on every visit.

You connect one Solana wallet and one EVM wallet, or paste addresses to watch read-only. Several wallets per chain are fine.

## Claim everything at once

**Claim all** collects fees from every position on every chain. Tidepool groups the transactions per chain and asks for one signature per group. On Uniswap v3, the collect, an optional sell to one token and the platform fee go in one Universal Router transaction. On Solana, claims for several positions go in one batch of signatures.

## Move capital between chains

The Deposit sheet bridges from inside the app. Across handles the routes between Base, Robinhood Chain and Arc (USDC or ETH; Robinhood Chain receives USDG, and Arc receives USDC, which is also its gas token). Relay handles any route that touches Solana with one signature; the solver pays the destination gas. You can go from a closed DLMM position on Solana to a new Uniswap position on Base without leaving Tidepool.

## What to watch when you LP on several chains

-   **Fee units differ.** DLMM pools quote a base fee plus a variable fee that rises with volatility. Uniswap v3 pools have a fixed tier. Uniswap v4 pools can have a dynamic fee set by a hook. Compare pools by fee to TVL over a window, not by the fee number.
-   **Range mechanics differ.** DLMM uses bins with a strategy shape (spot, curve, bid-ask). Uniswap uses ticks with liquidity spread evenly across the range. A "wide" range means something different on each.
-   **Transaction ordering differs.** Solana and Base reward priority fees. Robinhood Chain (Arbitrum Nitro) and Arc are first come, first served. Tidepool's speed setting applies where it matters and is ignored where it does not.
-   **Stale data is dangerous.** A claim or close based on an old listing can double-pay or double-sell. Tidepool re-reads the position on chain before every action and sizes sells from real balance changes.
-   **Hooks can eat fees.** Some Uniswap v4 pools pay LPs nothing. Tidepool reads swap events and hides those pools.

## Learn from other LPs

Tidepool's feed shows entries other LPs made, with the pool, the range and a thesis note, across all chains. The leaderboard ranks wallets by realized plus unrealized PnL over 24h, 7d, 30d and all time. Tap "Enter this position" to open the wizard with the same pool and range.

## Start

1.  Open [tidepool.ag](https://tidepool.ag/) and connect or paste an address.
2.  Check Portfolio for fees you have not claimed.
3.  Look at Search sorted by 24h fee to TVL across chains.
4.  Bridge to the chain that pays, open the position, and claim from one screen from then on.

---

Source: [tidepool.ag/guides/cross-chain-lp-management](https://tidepool.ag/guides/cross-chain-lp-management). The website is the canonical version of this page.
