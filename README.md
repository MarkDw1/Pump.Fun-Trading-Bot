**>>WARNNING ON SCAMS IN ISSUES COMMENT SECTION<<**

The issues comment section is often targeted by scam bots willing to redirect you to an external resource and drain your funds.

I have enabled a GitHub actions script to detect the common patterns and tag them, which obviously is not 100% accurate.

This is also why you will see deleted comments in the issues—I only delete the scam bot comments targeting your private keys.

The official maintainers are in the [MAINTAINERS.md](MAINTAINERS.md) file.

Not everyone is a scammer though, sometimes there are helpful outside devs who comment and I absolutely appreciate it.

**>>END OF WARNING<<**

Development ongoing at [refactored/main-v2](https://pumpfun-sniperbot.com) branch.

As of March 21, 2025, the bot from the **refactored/main-v2** branch is signficantly better over the **main** version, so the suggestion is to FAFO with v2.

Leave your feedback by opening **Issues**.

A word warning:

**Not For Production (NFP)**

This code is not intended for production use. Feel free to take the source, modify it to your needs, and most importantly, **learn from it**.

We assume no responsibility for the code or its usage. This is our public service contribution to the community and Web3.

# Pump.fun bot development roadmap

| Stage | Feature | Comments | Implementation status
|-------|---------|----------|---------------------|
| **Stage 1: General updates & QoL** | Lib updates | Updating to the latest libraries | ✅ |
| | Error handling | Improving error handling | WIP | 
| | Configurable RPS | Ability to set RPS in the config to match your provider's and plan RPS (preferably [Chainstack](https://console.chainstack.com/) 🤩) | WIP |
| | Dynamic priority fees | Ability to set dynamic priority fees | ✅ |
| | Review & optimize `json`, `jsonParsed`, `base64` | Improve speed and traffic for calls, not just `getBlock`. [Helpful overview](https://docs.chainstack.com/docs/solana-optimize-your-getblock-performance#json-jsonparsed-base58-base64).| ✅ | 
| **Stage 2: Bonding curve and migration management** | `logsSubscribe` integration | Integrate `logsSubscribe` instead of `blockSubscribe` for sniping minted tokens into the main bot | ✅ |
| | Dual subscription methods | Keep both `logsSubscribe` & `blockSubscribe` in the main bot for flexibility and adapting to Solana node architecture changes | ✅ |
| | Transaction retries | Do retries instead of cooldown and/or keep the cooldown | WIP |
| | Bonding curve status tracking | Checking a bonding curve status progress. Predict how soon a token will start the migration process | WIP | 
| | Account closure script | Script to close the associated bonding curve account if the rest of the flow txs fails | ✅ |
| | PumpSwap migration listening | pump_fun migrated to their own DEX — [PumpSwap](https://x.com/pumpdotfun/status/1902762309950292010), so we need to FAFO with that instead of Raydium (and attempt `logSubscribe` implementation) | ✅ |
| **Stage 3: Trading experience** | Take profit/stop loss | Implement take profit, stop loss exit strategies | FAFO |
| | Market cap-based selling | Sell when a specific market cap has been reached | Not started |
| | Copy trading | Enable copy trading functionality | Not started |
| | Token analysis script | Script for basic token analysis (market cap, creator investment, liquidity, token age) | Not started |
| | Archive node integration | Use Solana archive nodes for historical analysis (accounts that consistently print tokens, average mint to raydium time) | Not started |
| | Geyser implementation | Leverage Solana Geyser for real-time data stream processing | ✅ |
| **Stage 4: Minting experience** | Token minting | Ability to mint tokens (based on user request - someone minted 18k tokens) | FAFO |


