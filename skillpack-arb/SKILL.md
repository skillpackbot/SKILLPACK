---
name: skillpack-arb
description: Find and optionally execute price differences for the same token between Base and Robinhood Chain. Use when the user asks about arbitrage, price difference, arb opportunity, or wants to profit from Base vs Robinhood spreads.
tags: [arbitrage, arb, base, robinhood, cross-chain]
version: 1
---

# Skillpack Arb

Detect and act on price discrepancies of the same token across **Base** and **Robinhood Chain**.

## When to activate
- “any arb between base and robinhood?”
- “is $TICKER cheaper on robinhood?”
- “find arbitrage opportunities”
- User wants to buy low on one chain and sell high on the other

## Workflow

### 1. Identify candidates
- Tokens that exist on both chains (especially LayerZero OFT tokens)
- High-volume pairs
- Recently bridged tokens that may have thin liquidity on one side

### 2. Price check
For each candidate:
- Spot price on Base
- Spot price on Robinhood
- Spread % after estimated gas + bridge fees
- Liquidity depth on both sides

### 3. Opportunity filter
Only surface opportunities where:
- Spread > estimated total cost (bridge + gas + slippage)
- Sufficient liquidity to size the trade reasonably

### 4. Execution (optional)
If user wants to take the arb:
1. Buy on the cheaper chain
2. Bridge via `skillpack-bridge` (or existing OFT)
3. Sell on the more expensive chain
4. Report net profit after all costs

## Output format
```
Token: $TICKER
Base price: $0.00042
Robinhood price: $0.00048
Raw spread: +14.3%
Est. costs: ~3.1%
Net edge: ~11.2%
Suggested size: $800
```

## Notes
- Arbitrage edges can disappear quickly.
- Always simulate full round-trip cost before recommending size.
- Prefer tokens with existing OFT bridges for faster execution.
```
