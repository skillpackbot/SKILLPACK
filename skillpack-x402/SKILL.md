---
name: skillpack-x402
description: Helpers for x402 payments — charge users per action, accept tips, or gate premium skill features with USDC on Base. Use when the user wants paid skills, x402, pay-per-use, tips, or monetization of agent actions.
tags: [x402, payments, monetization, usdc, tips, paid]
version: 1
---

# Skillpack x402

Simple helpers for **x402** (pay-per-request) style monetization on Base.

## When to activate
- “make this skill paid”
- “charge $0.10 per use”
- “add tip jar”
- “x402 payment”
- User wants to monetize agent actions or content

## Core ideas
x402 lets visitors pay small amounts of USDC on Base to trigger an action or unlock a response. Bankr already supports x402 flows for apps and tools.

## Common patterns this skill supports

### 1. Pay-per-action
- Define price (e.g. $0.05 – $1.00 USDC)
- On request: create payment intent → wait for settlement → execute the action
- Return result only after successful payment

### 2. Tip / donation
- Provide a simple “tip $1 / $5 / $10” flow
- Funds go to the agent or creator wallet

### 3. Gated premium feature
- Free tier does basic work
- Premium tier (after x402 payment) unlocks deeper research, larger size, or private data

## Workflow when implementing
1. Confirm price and recipient wallet
2. Generate the x402 payment request (Bankr native helpers)
3. After confirmation of payment, run the paid logic
4. Log the payment for the creator

## Example prompts
- “charge 0.10 USDC every time someone asks for alpha”
- “add a tip button for my agent”
- “make the deep research feature cost $0.50 via x402”

## Notes
- Stick to Base for lowest friction (USDC + gas sponsorship).
- Keep prices low for high conversion.
- Always show clear confirmation of what the user is paying for.
