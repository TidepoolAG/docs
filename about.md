# What is Tidepool?

Tidepool (tidepool.ag) is a non-custodial liquidity position manager for Meteora on Solana and Uniswap v3 and v4 on Base, Robinhood Chain and Arc. Every LP position, every chain, one place.

Concentrated-liquidity DEXes pay the best fees in DeFi, but each one has its own app, its own wallet flow and its own way to show a position. If you provide liquidity on more than one chain, you spend your time switching tabs. Tidepool puts the positions side by side, shows what each one earns, and lets you act on all of them from one screen.

## What you can do

-   **Track.** Portfolio value, claimable fees, PnL per position, range and current price, on Solana, Base, Robinhood Chain and Arc together. Watch any address read-only, no wallet needed.
-   **Find pools.** Search by name or paste any pool or token address. Pools rank by fee to TVL, volume and age, with tokenized stocks (xStocks, Robinhood tokens) as a filter.
-   **Open.** A four-step wizard: pool, range, amount, confirm. Enter with one token and Tidepool swaps into the split the range needs, through Jupiter on Solana or the pool itself on EVM.
-   **Claim.** One tap per position, or "Claim all" across every chain. Uniswap v3 claims can sell the fees to one token in the same transaction.
-   **Close and zap out.** Close a position and swap everything to one token in one flow.
-   **Bridge.** Move funds between Solana, Ethereum, Base, Robinhood Chain, Arc and HyperEVM from inside the app through Relay, with gas on arrival when you have none yet.
-   **Share.** Profiles, a feed of entries with thesis notes, and a PnL leaderboard so you can follow LPs who do well and enter the same positions.

## Supported chains and DEXes

| Chain | DEX | Track | Open, claim, close |
| --- | --- | --- | --- |
| Solana | Meteora DLMM, Meteora DAMM v2 | Yes | Yes |
| Base | Uniswap v3, Uniswap v4 | Yes | Yes |
| Robinhood Chain | Uniswap v3, Uniswap v4 | Yes | Yes |
| Arc | Uniswap v3, Uniswap v4 | Yes | Yes |
| HyperEVM (Hyperliquid) | Project X | Yes | Yes |
| Ethereum | Uniswap v3, Uniswap v4 | Yes | Claim and close only |

## Non-custodial by design

Tidepool never holds keys or funds. You connect a wallet you already use (Phantom, Solflare or Backpack on Solana; MetaMask, Rabby, Phantom or Coinbase Wallet on EVM; WalletConnect for mobile browsers) and sign every transaction yourself. Positions are the same NFTs and accounts the DEX itself creates, so you can always manage them in the DEX app too. Every claim and close starts from a fresh on-chain read of the position, never from a cached listing.

## Pricing

Tidepool takes 3% of the fees you claim through the app, and 1% on Robinhood Chain. The fee is paid in SOL or ETH value inside the same transaction, so there is nothing to approve separately. There is no subscription, no fee on swaps, no fee on deposits and no token.

## Where the data comes from

Positions and fees are read from the chain and from the Meteora data APIs. Pool discovery, volume and candles come from GeckoTerminal, prices from CoinGecko, charts from TradingView Lightweight Charts. Tidepool does not run its own indexer that could show you stale numbers.

## What Tidepool is not

-   **Not Tidepool.org.** That is a nonprofit that builds diabetes software. Tidepool at tidepool.ag is an unrelated DeFi application for liquidity providers. When you search for the LP tool, add "tidepool.ag" or "Tidepool DeFi".
-   **Not a token screener or rug checker.** Tidepool does not score tokens for safety. It ranks pools by the fees they pay and manages your positions in them.
-   **Not the open-source "Tidepool" pool screening tool on GitHub.** A separate hobby project with the same name (a Solana token and Meteora pool risk scanner at tidepool.rizarma.com) is not tidepool.ag and is not made by us. The official Tidepool.ag GitHub organisation is [github.com/TidepoolAG](https://github.com/TidepoolAG), with docs and brand files only; the app source is not public.
-   **Not a trading bot.** Tidepool does not buy or sell on your behalf. You sign every transaction.
-   **Not connected to the Robinhood brokerage.** Tidepool supports Robinhood Chain, the public Ethereum layer 2, through Uniswap v3 and v4. It has no link to Robinhood brokerage accounts.
-   **Not Solana-only.** Tidepool manages Meteora positions on Solana and Uniswap positions on Base, Robinhood Chain and Arc in the same portfolio. Cross-chain is the point.

---

Source: [tidepool.ag/about](https://tidepool.ag/about). The website is the canonical version of this page.
