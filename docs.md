# Tidepool docs

What providing liquidity is, what you earn, what you risk, and how to do it in Tidepool from the first click to the last.

-   [What an LP does](#what)
-   [Why the range decides everything](#range)
-   [What you earn and what you risk](#earn)
-   [Price swings and impermanent loss](#il)
-   [Walk through the app](#walk)
-   [Claiming fees](#claim)
-   [Closing, zapping and rebalancing](#exit)
-   [Stop loss and take profit](#auto)

## What an LP does

Every swap on a decentralised exchange trades against a pool of two tokens that other people put there. Those people are liquidity providers. The trader pays a fee on every swap, and that fee goes to the providers in proportion to how much of the traded liquidity was theirs.

You are not lending and you are not betting on a direction. You are holding both tokens of a pair and being paid for letting others trade against them. While the price moves inside your range, the pool keeps selling you the token that falls and buying the token that rises, and you collect a fee each time.

Trader swaps SOL for TOKEN pays a fee Pool SOL TOKEN deposit fees You, the LP earn a share of every swap fee

A trader swaps against the pool. Part of what they pay goes to whoever supplied the liquidity they used.

## Why the range decides everything

Old pools spread your money across every price from zero to infinity. Almost none of it sat near the price where trading actually happens, so almost none of it earned. Concentrated liquidity fixed that: you choose a price range, and all of your money works inside it.

Narrow it and the same money earns a bigger share of every swap. Narrow it too far and the price walks out, your position stops trading, and it earns nothing until the price comes back.

WIDE RANGE 1× depth at the price price NARROW RANGE, SAME MONEY 4× depth price

The same deposit in a quarter of the width stands four times deeper at the price, so it takes about four times the share of each swap there. Concentration is the whole idea, and the whole risk.

Where the price sits inside your range decides what you are holding:

Price below your range earns nothing all TOKEN price Price inside your range earns fees SOLTOKEN price Price above your range earns nothing all SOL price

The pool sells you the token that falls, so below the range you end up holding all of it. Tidepool shows the range as the blue band on every chart, and says _in range_ or _out of range_ on the card.

## What you earn and what you risk

Two forces pull in opposite directions.

**Fees.** Every swap through your range pays you. A busy pool with a high fee and a narrow range can pay a lot in a day. Tidepool ranks pools by _24h fee to TVL_, which is the fee the pool paid over the money sitting in it. Ten percent means the pool paid a tenth of its own size in fees in a day.

**The price moving.** Fees are the income. Price swings are the cost, and the next section explains why.

## Price swings and impermanent loss

Inside your range the pool trades against you on every move. When the token falls, the pool uses your SOL to buy more of it. When the token rises, the pool sells your token for SOL. So you always hold more of what went down and less of what went up.

-   **Price falls out of the bottom.** The pool has bought the token all the way down. You hold only the token and take the rest of the fall in full.
-   **Price rises out of the top.** The pool has sold all of your token on the way up. You hold only SOL and miss the rest of the rise.
-   **Price swings up and down inside the range.** This is the best case. Every pass earns fees, and when the price comes back, the trades undo themselves.

**Impermanent loss** is the name for that cost: how much less your position is worth than if you had simply held the two tokens you put in. It is _impermanent_ because it shrinks back to zero if the price returns to where you entered. It becomes permanent when you close the position while the price is away.

your range $70$80$90$100$110 holdingLP positionimpermanentloss −30%0+30% token price since you entered

$100 in a range of plus and minus 10%, half SOL and half token, with SOL as the measure. The position is never worth more than holding. The red gap is the impermanent loss that fees must beat.

A narrow range makes this stronger in both directions. It earns more fees per dollar, and it loses more to the same move. A 10% fall costs a range of plus and minus 10% about 2.6% against holding. A position over the full price range (the old way) loses about 0.1% on the same move.

A worked example, from the chart above. You put in $100, half SOL and half token, in a range of plus and minus 10%. The token falls 20% and leaves your range. You now hold only the token, worth about $82. Simply holding would have left you at $90, so the impermanent loss is about $8. With $6 of fees you are at $88: fees paid for most of the move, but not all of it. If the token had moved up and down inside the range instead, the same $6 would have been nearly all profit.

So the question is never only "did I earn fees". It is "did fees beat the impermanent loss". Busy pools with a high fee to TVL, a range that fits how much the price really moves, and closing or rebalancing before a trend runs far are how LPs win that race.

## Walk through the app

1.  **Connect, or just watch.** Tap _Connect wallet_ for Phantom, Solflare, Backpack, MetaMask, Rabby or Coinbase Wallet. Or tap _Watch an address_, paste any Solana or EVM address, and look without signing anything.
2.  **Find a pool.** Search ranks pools by what they actually paid, across Solana, Base, Robinhood Chain and Arc at once. Switch the window between 24h, 7d and 30d. Filter tokenised stocks in or out. Paste a token or pool address from any chain and Tidepool works out which chain it is.
3.  **Pick a range.** Drag the two handles on the candle chart, or use the presets. The bar under the chart shows where your money will sit, green for the quote token below the price and blue for the other token above it.
4.  **Choose a shape and an amount.** On Meteora, Spot spreads it evenly, Curve piles it near the price, Bid-Ask pushes it to the edges. Pay with one token and Tidepool works out the split and swaps the rest for you.
5.  **Review and sign.** The last step shows the deposit, the estimated fees per day, the swap cost, the gas and the rent that comes back when you close.

![Tidepool Search, ranking pools by 24h fee to TVL across four chains](/img/search.webp)

Search, ranked by what pools really paid

![Choosing a price range on a candle chart with draggable handles](/img/range.webp)

Drag the range on the chart

![Picking a Meteora shape and the amount to deposit](/img/deposit.webp)

Shape, amount, and what it will cost

## Claiming fees

Fees do not compound by themselves. They sit next to your position until you take them, on Meteora and on Uniswap alike. Taking them costs a transaction, so there is a point below which it is not worth doing yet.

-   **One position.** Open it in Portfolio and tap _Claim_. The sheet shows what you will receive.
-   **Everything at once.** _Claim all fees_ at the top of Portfolio takes every position on every chain. On Solana that is one wallet approval for the batch.
-   **Claim and sell.** The claim sheet can swap what you claimed into one token in the same breath. On Uniswap v3 it fits in a single transaction.

Claimed fees are yours to keep, redeploy, or compound by hand into the same position.

## Closing, zapping and rebalancing

-   **Close** takes the liquidity out and claims the fees with it. You get both tokens back.
-   **Zap out** does the same and then swaps everything into one token, so you end with just SOL, ETH or a stable.
-   **Rebalance** is for a position the price has left. It closes, swaps what the new range needs, and opens again in the same pool. Drag the new range on the chart like you did the first time. Your unclaimed fees go into the new position.

## Stop loss and take profit

You can arm an automatic exit, either when you open the position or later from the card. Set the price, choose what to receive, and Tidepool closes the position and swaps it into that token when the price gets there, whether or not the app is open.

It works through a one-time approval. The contract can remove your liquidity and pay _you_, and nothing else. Tidepool never holds your keys or your funds, and you can cancel or revoke at any time. An exit is a best effort, not a promise: it can run late or at a worse price than the trigger.

## Fees

3% of every claim, paid in SOL or ETH value inside the claim, close or zap transaction. No subscription, no fee on swaps, no fee on deposits.

## Safety rules

-   Tidepool never holds keys or funds. Positions stay in your wallet as the DEX's own NFTs and accounts.
-   Every claim and close starts from a fresh on-chain read of the position.
-   If a transaction result is uncertain (funds may have moved), Tidepool stops and shows you. It never retries automatically.
-   API keys for RPCs and price data live on the server, not in the browser bundle.

## Who moves your tokens

Swaps go through Jupiter on Solana and the Uniswap routers on EVM chains. Bridges go through Across and Relay. Tidepool never holds your funds in between.

## Known limits

-   Ethereum mainnet: track, claim and close only. No new positions.
-   Uniswap v4 pools with hooks that need hook data revert on open.
-   Meteora DLMM: one position account holds at most 69 bins. Wider ranges use several accounts.
-   Leaderboard PnL counts Meteora positions. Uniswap PnL is being added.

---

Source: [tidepool.ag/docs](https://tidepool.ag/docs). The website is the canonical version of this page.
