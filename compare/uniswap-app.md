# Tidepool vs the Uniswap app

The Uniswap app (app.uniswap.org) is the native interface for Uniswap v3 and v4. Tidepool manages the same positions on Base, Robinhood Chain and Arc, ranks pools by what they pay, and puts them next to your Meteora positions on Solana.

## What is the same

The positions. A Uniswap v3 position is an NFT from the NonfungiblePositionManager; a v4 position is an NFT from the v4 PositionManager. Tidepool mints, increases, collects and burns through those same contracts and the Universal Router, so positions move freely between the two apps.

## What Tidepool adds

|  | Tidepool | Uniswap app |
| --- | --- | --- |
| Chains | Base, Robinhood Chain, Solana (Meteora) | EVM chains, no Solana |
| Pool ranking | Fee to TVL, volume, TVL, age for 24h, 7d, 30d; active TVL for the range | TVL and volume lists |
| Claim and sell | v3: collect, sell fees to one token and pay in one Universal Router transaction | Collect, then swap separately |
| Claim all | Every position on every chain | Per position |
| One-token entry | Swap through the pool you are entering, then mint | Both tokens |
| Zap out | Burn and swap to one token in one flow | Remove, then swap |
| v4 hook fees | Reads the real fee from swap events for dynamic-fee hooks; hides pools that pay LPs nothing | Shows the pool key fee |
| Tokenized stocks | Filter for Robinhood tokens, Base equity tokens, Dinari, Ondo | No filter |
| Watch any address | Yes, read-only | Connect wallet |
| Bridging | Across and Relay inside the app, including to Solana | Uniswap bridge for EVM chains |
| Fee | 3% of claimed fees | Interface fee on swaps |

## Robinhood Chain

Tidepool supports Uniswap v3 and v4 on Robinhood Chain (chain id 4663), including the tokenized stock pools. Robinhood Chain is an Arbitrum Nitro chain, so Tidepool ignores priority fees there and orders by arrival. See the [Robinhood Chain LP guide](../guides/robinhood-chain-liquidity.md).

## When to stay in the Uniswap app

Ethereum mainnet liquidity (Tidepool tracks, claims and closes there but does not open), chains Tidepool does not support yet, and v4 pools whose hooks need hook data on mint.

Uniswap app facts as of September 2026..

---

Source: [tidepool.ag/compare/uniswap-app](https://tidepool.ag/compare/uniswap-app). The website is the canonical version of this page.
