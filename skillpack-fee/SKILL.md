---
name: skillpack-fee
description: Track, claim, and report creator trading fees from tokens launched on Base or Robinhood Chain. Use when the user asks about fees, earnings, claim fees, fee revenue, or how much they have earned from their tokens.
tags: [fees, claim, earnings, creator, base, robinhood]
version: 1
---

# Skillpack Fee

Monitor and claim creator fees from tokens launched via Bankr on Base and Robinhood Chain.

## When to activate
- “how much fees have I earned?”
- “claim my fees”
- “show fee revenue”
- “check creator earnings for token 0x…”

## Workflow

### 1. Discover tokens
- List all tokens where the current wallet is the fee recipient / creator.
- Support both Base and Robinhood Chain.
- Allow user to specify a single token address.

### 2. Fetch fee data
For each token show:
- Unclaimed fees (in ETH / WETH / native)
- Total fees earned (lifetime)
- 24h / 7d fee volume
- Current claimable amount

### 3. Claim
- If user wants to claim: execute claim transaction(s).
- Prefer claiming on the chain where fees are highest first.
- Confirm success and new wallet balance.

### 4. Reporting
Provide a clean summary:
```
Token: $TICKER (0x…)
Chain: Base
Unclaimed: 0.42 ETH (~$1,250)
Lifetime: 12.8 ETH
24h fees: 0.08 ETH
```

## Example prompts
- “claim all my fees”
- “how much have I earned from my tokens this week?”
- “show fee status for 0x…”
- “transfer claimed fees to my main wallet”

## Notes
- Fees accrue in real time from the 0.7% swap fee (majority to creator).
- Some launches may have additional protocol / LP fees — only claim the creator portion.
- After claiming, suggest using fees to fund agent compute (`skillpack-agent`).
```
