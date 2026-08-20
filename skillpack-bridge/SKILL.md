---
name: skillpack-bridge
description: Bridge tokens between Base and Robinhood Chain using LayerZero OFT, optionally seed a liquidity pool on the destination chain. Use when the user wants to bridge, expand a token to Robinhood, move assets Base ↔ Robinhood, or bootstrap liquidity after bridging.
tags: [bridge, layerzero, base, robinhood, oft, liquidity]
version: 1
---

# Skillpack Bridge

Bridge tokens between **Base** and **Robinhood Chain** using LayerZero OFT. Optionally create and seed a Uniswap pool on the destination chain so the token is immediately tradable.

## When to activate
- User says “bridge … to robinhood / to base”
- User wants to make a Base token available on Robinhood Chain
- User asks to expand a token omnichain or seed liquidity after bridge

## Core workflow

### 1. Confirm parameters
Ask or extract:
- Token address (or ticker if known)
- Source chain (Base or Robinhood)
- Destination chain
- Amount to bridge
- Optional: seed liquidity amount (e.g. “$5k WETH pool”)
- Recipient address (default: user’s Bankr wallet)

### 2. Check existing bridge
- Look for existing LayerZero OFT Adapter (Base side) and OFT (Robinhood side).
- If the token is already bridged, use the existing contracts.
- If not, deploy the full bridge setup (Adapter + OFT + peer configuration).

### 3. Execute bridge
Typical flow Base → Robinhood:
1. Approve OFTAdapter if needed
2. Build SendParam (dstEid for Robinhood ≈ 30416, amount, recipient as bytes32)
3. Quote nativeFee via quoteSend
4. Call send with the quoted fee
5. Wait for LayerZero message delivery

Reverse direction (Robinhood → Base) follows the symmetric OFT flow.

### 4. Optional liquidity seed
If user requested a pool:
- Create Uniswap V3/V4 pool on destination (usually paired with WETH)
- Add the requested liquidity
- Confirm pool address and initial price

### 5. Report results
Always return:
- Source and destination tx hashes
- Bridged amount
- Destination token address
- Pool address (if created)
- New balances on both chains

## Example prompts this skill handles
- “bridge 10000 BNKR to robinhood”
- “launch my token 0x… from base to robinhood chain with a $10k weth pool”
- “bridge $500 of ETH from base to robinhood”
- “move my token to robinhood and seed liquidity”

## Safety rules
- Always confirm amount and destination before signing.
- Prefer gas-sponsored paths when available on Base.
- Warn if liquidity seed amount is very small (high slippage risk).
- Never bridge more than the user’s available balance.
