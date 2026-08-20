---
name: skillpack-portfolio
description: Multi-chain portfolio tracker and PnL focused on Base and Robinhood Chain. Use when the user asks for balances, portfolio value, PnL, holdings, or a snapshot of their positions across these chains.
tags: [portfolio, balances, pnl, tracker, base, robinhood]
version: 1
---

# Skillpack Portfolio

Clean portfolio view optimized for **Base + Robinhood Chain**.

## When to activate
- “what’s my portfolio?”
- “show balances on base and robinhood”
- “how much am I up/down?”
- “list my holdings”

## What to show

### Snapshot
- Total value (USD)
- Breakdown by chain (Base vs Robinhood)
- Top positions by value
- Native balances (ETH) + major stables

### Token details
For each significant holding:
- Token + chain
- Amount
- Current price & value
- 24h change (if available)

### Optional PnL
- If cost basis is known or can be estimated from recent buys
- Unrealized PnL per position and total

### Creator section (if relevant)
- Tokens launched by the user
- Unclaimed fees (link to `skillpack-fee`)

## Output format example
```
Portfolio Snapshot
Total: $12,480

Base: $9,210
- ETH: 1.2 ($3,900)
- BNKR: 2.1M ($4,100)
- Other: $1,210

Robinhood: $3,270
- NVDA stock token: $1,800
- AAPL stock token: $900
- ETH: 0.18 ($570)

Unclaimed fees: 0.31 ETH
```

## Actions
- Refresh prices
- Drill into a single token
- Suggest rebalancing or claiming fees
- Export simple summary
```
