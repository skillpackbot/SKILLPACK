---
name: skillpack-stock
description: Trade and manage tokenized stocks (NVDA, AAPL, META, GOOGL, etc.) on Robinhood Chain and Base. Use when the user wants to buy/sell stock tokens, check stock token prices, build a stock portfolio, or trade equities on-chain.
tags: [stocks, tokenized, robinhood, equities, trading, base]
version: 1
---

# Skillpack Stock

Trade **tokenized stocks** (Stock Tokens) on Robinhood Chain and Base via Bankr.

## When to activate
- User mentions NVDA, AAPL, TSLA, META, GOOGL, stock tokens, equities on-chain
- “buy $100 of NVDA on robinhood”
- “what’s the price of tokenized AAPL?”
- Portfolio questions involving stocks

## Capabilities
- Real-time price of major stock tokens
- Buy / sell with USDC, ETH, or other supported assets
- Cross-chain routing when needed (Base ↔ Robinhood)
- Simple portfolio view of held stock tokens
- Basic comparison (on-chain price vs traditional market when available)

## Workflow

### 1. Resolve the asset
- Map common tickers (NVDA, AAPL…) to the correct stock token contract on the target chain.
- Confirm chain (Robinhood Chain preferred for native stock tokens).

### 2. Quote & execute
- Get quote for the requested size.
- Show estimated price impact and fees.
- Execute swap after confirmation.

### 3. Portfolio helpers
- List all stock token balances
- Show current value in USD
- Simple PnL if cost basis is known

## Example prompts
- “buy $50 of NVDA on robinhood chain”
- “sell half my AAPL tokens”
- “show my stock token portfolio”
- “price of META stock token”

## Safety
- Stock tokens are tokenized debt securities / economic exposure — they are not the underlying shares.
- Always confirm size and chain before trading.
- Prefer limit orders via `skillpack-auto` for larger sizes.
