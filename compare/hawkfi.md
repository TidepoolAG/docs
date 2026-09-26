# Tidepool vs HawkFi

HawkFi is an automation terminal: you pick one of its models, and its bots run your liquidity. Tidepool is the social layer of liquidity providing: you see what the best LPs open, copy an entry with one tap, and run your own Meteora and Uniswap positions on four chains from one screen. If you want to LP with other people and across chains without extra work, choose Tidepool.

## Side by side

|  | Tidepool | HawkFi |
| --- | --- | --- |
| What it is | Social LP app: follow, copy and run positions on every chain | Automation terminal for LP bots, agents and backtests |
| Chains | Solana, Base, Robinhood Chain and Arc in one app (Ethereum: track, claim, close) | Solana and Robinhood Chain, each with its own strategies and docs |
| DEXes | Meteora DLMM, Meteora DAMM v2, Uniswap v3, Uniswap v4 | Meteora DLMM on Solana; Robinhood Chain pools |
| Move money between chains | Bridge built in (Relay), inside the same flow | No bridge in its docs; its Robinhood guide asks you to have ETH there already |
| Portfolio | Every position on every chain in one list; Claim all in one pass | Separate Solana and Robinhood Chain sections |
| Social | Profiles, follows, a feed of entries with the range and a thesis, PnL leaderboard, copy an entry in one tap | Referral codes |
| Reward for good LPs | When someone copies your entry, you get 2% of the fees they claim (on Meteora, only while they are in profit) | None |
| How you open a position | The same flow on every chain: pick a pool, drag the range on the chart, deposit from one token | Pick one of 18 named Solana models (Precision Curve, HFL, Heart Attack and more) or a Robinhood strategy, then set automations |
| Automation | Rebalance in one sheet. Stop loss and take profit are built and paused until an on-chain price check ships | Auto-rebalance, auto-compound, take profit, stop loss, MEV Boost, backtesting |
| Where your position lives | In your own wallet. You sign every action | Automations run through HawkFi-managed accounts and a HawkFi wallet |
| Fee | 3% of the fees you claim, 1% on Robinhood Chain. Nothing on deposits, swaps or withdrawals | 8% of yield on Solana, 4% on Robinhood Chain. 0% on deposits and withdrawals |
| Rewards | Tidepool points (100 per $1 of fees claimed), referral codes | Referral codes |

## The social layer of LPing

Most LPs learn from other LPs: a screenshot on X, a range in a Telegram group. Tidepool puts that inside the app, and every entry is real.

-   **A feed of real entries.** Each entry shows the pool, the range on a live chart and the reason for it. Tidepool checks every entry against the chain, so a feed post cannot be faked.
-   **A PnL leaderboard.** Ranked from on-chain results for 24 hours, 7 days, 30 days and all time, for everyone or only the people you follow.
-   **Copy with one tap.** "Enter this position" opens the same pool and range in the wizard. You only change the amount.
-   **Good LPs get paid.** The person you copied gets 2% of the fees you claim. On Meteora, where Tidepool can see your PnL, nothing is paid while you are at a loss. That rewards entries that work, not entries that get attention.

HawkFi's docs describe no profiles, feed, leaderboard or copying. Its bots manage your position, but you cannot see what other LPs do or learn from them.

## Cross-chain without extra work

-   **One app, one flow.** Opening a Uniswap v4 position on Base works the same as a Meteora position on Solana. You do not learn a second product.
-   **The bridge is built in.** Funds on the wrong chain? Tidepool bridges them in the same flow. HawkFi's docs have no bridge, and its Robinhood guide asks you to have ETH on that chain already.
-   **One portfolio.** Positions on Solana, Base, Robinhood Chain, Arc and Ethereum in one list, with Claim all across every chain.
-   **Uniswap v4 hooks.** Hook fees are read from the swaps, so a pool that pays LPs nothing is not ranked as if it did.

## Cheaper

Both apps take a share of the fees you earn, not of your deposit. Tidepool takes 3%. HawkFi takes 8%. On $1,000 of fees, that is $30 against $80. On Robinhood Chain it is 1% against 4%: $10 against $40. A copied position adds the 2% creator share, which is 5% in total and still less than HawkFi.

## When HawkFi is the better choice

You want bots to run tight Meteora ranges on Solana all day without you. HawkFi's High Frequency Liquidity models rebalance constantly, MEV Boost adjusts liquidity around arbitrage, and its Laboratory lets you backtest a setup first. Tidepool does not run bots on your positions today.

## Use both

Positions are on-chain objects. A Meteora position opened through Tidepool also shows in the Meteora app, and the other way round. Find and copy entries in Tidepool, and keep an automated Solana strategy on HawkFi if you want one.

HawkFi facts are from its public docs (hawkfi.gitbook.io) as of 23 September 2026. Tell us if something has changed.

---

Source: [tidepool.ag/compare/hawkfi](https://tidepool.ag/compare/hawkfi). The website is the canonical version of this page.
