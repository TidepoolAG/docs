# Security

Tidepool never holds your keys or your funds. You sign every transaction in your own wallet, and your positions are the same accounts and NFTs that Meteora and Uniswap create. This page lists what you sign, which contracts your transactions use, and how to check it yourself.

## What you sign

-   **Connecting a wallet** shares your public address only. Signing in to a profile is a text message: it costs nothing and moves no funds. [What access Tidepool gets](https://tidepool.ag/docs#wallet-access).
-   **Every action is a transaction you approve** in your wallet: open, add, claim, close, swap, bridge. Tidepool cannot move anything without that approval.
-   **Tidepool tests transactions before your wallet opens** where the chain allows it: claims, joined claim-and-sell transactions on Solana, and batches on EVM chains. A step that would fail is left out or named, and nothing is sent.
-   **An unclear transaction is never sent twice.** When the outcome of a transaction is unknown, Tidepool tells you to check your wallet and does not retry it.

## Which programs and contracts your transactions use

Your transactions go to the DEXes and routers below, never to an address of Tidepool, except the fee (see Fees) and the stop-loss contract when you use it.

| Chain | What | Address |
| --- | --- | --- |
| Solana | Meteora DLMM | `LBUZKhRxPF3XUpBCjp4YzTKgLccjZhTSDM9YuVaPwxo` |
| Solana | Meteora DAMM v2 | `cpamdpZCGKUy5JxQXB4dcpGPiikHawvSWAd6mEn1sGG` |
| Solana | Jupiter swaps | `JUP6LkbZbjS1jKKwapdHNy74zcZ3tLUZoi5QNyVTaV4` |
| Solana | Memo (a text note that marks a copied position) | `MemoSq4gqABAXKb96qnH8TysNcWxMyWCqXgDLGmfcHr` |
| Solana | Jito tips (a small priority payment to block builders) | Jito's public tip accounts |
| Base, Robinhood Chain, Arc, Ethereum | Uniswap v3 and v4 position managers, Universal Router, Permit2 | The official addresses in [Uniswap's deployment list](https://developers.uniswap.org/contracts/v4/deployments) |
| HyperEVM | Project X position manager (a Uniswap v3 fork) | `0xeaD19AE861c29bBb2101E834922B2FEee69B9091` |
| All chains | Bridging and some swaps | [Relay](https://relay.link) |

## Tidepool's own contract: TidepoolExit

TidepoolExit runs stop loss and take profit for Uniswap positions while your wallet is offline. It has the same address on Base, Robinhood Chain and Arc:

`0xdB452848e20Fc0429eCF8998E2Ad69B92df9594b`

Its source code is published and verified with an exact match on [Sourcify](https://sourcify.dev/#/lookup/0xdB452848e20Fc0429eCF8998E2Ad69B92df9594b) for all three chains.

-   **What it can do:** act only on an order that the position owner signed, only once, only before the order's deadline, and only while the pool price is past the trigger. It removes the liquidity, swaps through Uniswap pools only, and sends the result to the owner. The owner receives at least the value they signed for. It keeps no funds between transactions.
-   **What it cannot do:** send your funds to any other address, or act on a position without your signed order.
-   **Status:** new stop-loss orders are paused since 22 September 2026. Orders you made before still run, and you can cancel them at any time. The contract has not had an external audit yet. A second version, with stronger price checks, will only go live after an external audit.
-   **The approval it needs:** to arm a stop loss, you allow the contract to manage your Uniswap position NFTs. You can remove that approval at any time, for example with [revoke.cash](https://revoke.cash).

## Approvals

On EVM chains, a deposit or swap needs a one-time token approval for Uniswap's Permit2, Uniswap's position manager or the Relay router. Tidepool asks only for the contracts on this page. You can check and remove approvals at any time on [revoke.cash](https://revoke.cash).

## Fees

Tidepool takes 3% of the fees you claim (1% on Robinhood Chain). The fee is part of the claim transaction, so you see it in your wallet before you approve. It goes to these addresses only:

-   Solana: `4QcK3iNu9breEPJR8u2KqswZEvtuBXoSDcrdPonfqgBP`
-   EVM chains: `0x016cb3D1C9B49431Bc86A678F362278de1f95236`

For a copied position, 2% of the claimed fees go to the wallet of the person or bot you copied, inside the same claim. For a referred wallet, the referrer's share is paid the same way.

## Wallet warnings

Wallet security scanners trust well-known sites. A new site can get a warning even for a normal transaction. An LP deposit also looks unusual to a scanner: your tokens leave the wallet, and the position you get back is not a token the scanner can value. Check the transaction yourself:

-   Make sure the address bar says **tidepool.ag**.
-   The programs and contracts in the prompt must be the ones listed on this page.
-   Tidepool never asks for your seed phrase or private key, and never asks you to sign a message that moves funds. If anything asks for that, stop.

## Sanctions screening

Wallets on the US OFAC sanctions list cannot make a profile, sign in, be linked to a profile or receive payouts. The list is refreshed every day.

## Your data

What Tidepool stores and why is in the [privacy policy](https://tidepool.ag/privacy). The terms are at [/terms](https://tidepool.ag/terms).

## Report a security problem

Send it to [hello@tidepool.ag](mailto:hello@tidepool.ag) with "Security" in the subject. Please do not post it in public before we have answered. The same contact is in [security.txt](https://tidepool.ag/.well-known/security.txt).
