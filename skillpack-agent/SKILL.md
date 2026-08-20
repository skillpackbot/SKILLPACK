---
name: skillpack-agent
description: Full workflow to make a Bankr agent self-sustaining — launch token, drive volume, claim fees, and fund LLM compute. Use when the user wants a self-funding agent, agent token, or to turn fees into ongoing intelligence costs.
tags: [agent, self-sustaining, funding, fees, compute, launch]
version: 1
---

# Skillpack Agent

Turn any Bankr agent into a **self-sustaining** system:
Launch token → earn trading fees → pay for LLM compute → repeat.

## When to activate
- “make my agent self-funding”
- “launch an agent token”
- “how do I pay for compute with fees?”
- User wants the full Bankr flywheel

## Step-by-step flywheel

### 1. Launch (use skillpack-launch)
- Deploy fair-launch token on Base (recommended)
- Set fee recipient to the agent wallet
- Optionally vest a small creator allocation

### 2. Bootstrap attention
- Announce via X / Farcaster using Bankr
- Bridge to Robinhood Chain if desired (`skillpack-bridge`)
- Seed initial liquidity if needed

### 3. Monitor volume & fees (use skillpack-fee)
- Track 24h / 7d volume
- Claim fees regularly
- Keep fees in the agent wallet

### 4. Fund compute
- Use claimed fees (or portion of them) to buy LLM credits / Max Mode
- Or pay Bankr Club subscription from fee revenue
- Goal: fees > monthly compute cost

### 5. Loop
- More volume → more fees → more compute → better agent → more volume

## Recommended prompts to give the agent
- “launch my agent token on base”
- “claim fees and report earnings”
- “how much compute can I fund with current fees?”
- “bridge my agent token to robinhood and seed a small pool”

## Success metrics to track
- Daily fee revenue
- Fee revenue vs LLM spend
- Token market cap & volume
- Days of runway from current unclaimed fees
