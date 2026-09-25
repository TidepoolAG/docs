# Tidepool vs the Meteora app

The Meteora app (app.meteora.ag) is the native interface for Meteora DLMM and DAMM v2 pools on Solana. Tidepool manages the same positions, and adds everything the Meteora app cannot show: your Uniswap positions on Base, Robinhood Chain and Arc, cross-chain claims, bridging and a feed of other LPs.

## What is the same

The positions. A DLMM or DAMM v2 position is an on-chain account owned by your wallet. Tidepool opens positions with Meteora's own program instructions and the Meteora SDK, so a position opened in Tidepool appears in the Meteora app, and a position opened in the Meteora app appears in Tidepool. You can always fall back to the Meteora app.

## What Tidepool adds

|  | Tidepool | Meteora app |
| --- | --- | --- |
| Chains | Solana, Base, Robinhood Chain | Solana |
| Uniswap v3 and v4 positions | Yes, side by side with Meteora | No |
| Claim all | Every position on every chain in one pass | Per pool |
| One-token entry | Swap and deposit in one Solana transaction when it fits | Auto-fill within the pool's own pair |
| Zap out | Close and swap to one token in one flow | Withdraw, then swap elsewhere |
| Watch any address | Yes, read-only, no wallet | Connect wallet |
| Bridging | Relay inside the app | No |
| Tokenized stocks filter | xStocks, Robinhood tokens, Dinari, Ondo | No filter |
| Feed and leaderboard | Follow LPs, copy an entry with its range, PnL ranking | No |
| Fee | 3% of claimed fees | Protocol fee only |

## When to stay in the Meteora app

Pool creation with launch-specific settings, Meteora's own points and rewards views, and anything that is Solana-only and needs the newest Meteora feature the same week it ships. Tidepool follows the Meteora SDK, so new instructions arrive a little later.

## When Tidepool wins

You hold liquidity on more than one chain, you claim fees more than once a day, or you want to see what other LPs enter and why. If all your positions are Meteora and all your time is in the Meteora app, Tidepool still gives you one-tap Claim all and a read-only view on the phone, but the biggest gains are for cross-chain LPs.

Meteora app facts as of September 2026..

---

Source: [tidepool.ag/compare/meteora-app](https://tidepool.ag/compare/meteora-app). The website is the canonical version of this page.
