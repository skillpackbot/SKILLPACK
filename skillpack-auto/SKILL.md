---
name: skillpack-auto
description: Set up and manage automated trading strategies (DCA, TWAP, limit orders, stop-loss) optimized for Base and Robinhood Chain. Use when the user wants automation, recurring buys, limit orders, stop losses, or scheduled trades.
tags: [automation, dca, twap, limit, stop-loss, orders, base, robinhood]
version: 1
---

# Skillpack Auto

Automation pack for **Base** and **Robinhood Chain**.

## When to activate
- “set a limit order…”
- “DCA $50 of ETH every day”
- “stop loss at -15%”
- “TWAP sell over 4 hours”
- Any recurring or conditional order request

## Supported order types
| Type | Description |
|------|-------------|
| **Limit** | Buy/sell at a specific price or better |
| **Stop-loss** | Sell if price drops to threshold |
| **Take-profit** | Sell if price rises to target |
| **DCA** | Recurring buys/sells on a schedule |
| **TWAP** | Time-weighted average price execution |

## Workflow

### 1. Parse intent
Extract:
- Asset + chain
- Side (buy/sell)
- Size (USD or token amount)
- Trigger condition or schedule
- Optional: expiry

### 2. Validate
- Sufficient balance / allowance
- Reasonable parameters (avoid dust sizes)
- Confirm chain support for the order type

### 3. Place order
- Use Bankr’s native trading engine / automation tools
- Confirm order ID and status
- Show how to cancel or modify later

### 4. Monitoring helpers
- List open orders
- Cancel specific or all orders
- Report fills

## Example prompts
- “DCA $20 of BNKR every day for 7 days on base”
- “limit buy NVDA stock token at $5 less than current price”
- “set stop loss on my position at -12%”
- “TWAP sell 50% of my bag over the next 6 hours”
- “show my open orders”

## Best practices
- Prefer Base for complex automations (full trading engine support).
- For stock tokens, default to Robinhood Chain.
- Always confirm size and trigger before placing.
- Suggest combining with `skillpack-fee` claims for recurring funding.
