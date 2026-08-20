---
name: skillpack-launch
description: Fair-launch ERC-20 tokens on Base or Robinhood Chain with fee sharing, liquidity lock, and optional vesting. Use when the user wants to launch a token, deploy a new coin, create a fair launch, or set up creator fees.
tags: [launch, token, fair-launch, base, robinhood, clanker, fees]
version: 1
---

# Skillpack Launch

Deploy fair-launch tokens on **Base** (primary) or **Robinhood Chain**. Creator receives the majority of trading fees automatically.

## When to activate
- User says “launch a token”, “deploy coin”, “fair launch”, “create token on base/robinhood”
- User wants to set up a self-funding agent token

## Default parameters (Bankr standard)
- Supply: 100 billion
- Pool: 85% of supply
- Vesting: 15% to creator (optional, usually 2-year linear with cliff)
- Swap fee: 0.7% (≈95% to creator / 5% to protocol)
- Liquidity: locked (no migration)

## Workflow

### 1. Collect details
- Token name & ticker
- Target chain (Base preferred, Robinhood if requested)
- Optional: vesting %, cliff, duration
- Optional: description / socials / image
- Confirm creator wallet (default: current Bankr wallet)

### 2. Deploy
- Use Bankr’s native launch tools (Clanker / Doppler style on Base, equivalent on Robinhood when available).
- Deploy token + pool in one flow.
- Liquidity is locked automatically.
- Fee recipient set to creator wallet.

### 3. Post-launch
- Return contract address, pool address, launch page URL
- Show how to claim fees later (`skillpack-fee`)
- Suggest bridging to the other chain with `skillpack-bridge` if user wants omnichain presence

### 4. Optional follow-ups
- Seed additional liquidity
- Announce on X / Farcaster via Bankr
- Set up automation with `skillpack-auto`

## Example prompts
- “launch a token called SkillPack ticker $SKILL on base”
- “fair launch my agent token on robinhood chain”
- “deploy token with 10% vested to me over 1 year”

## Best practices
- Prefer Base for first launch (more liquidity + full feature support).
- Keep name/ticker clean and memorable.
- Always confirm fee recipient address before deploy.
- Remind user that volume = fees → self-sustaining agent.
