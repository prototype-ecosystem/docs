+++
title = "Inverse Rewards"
description = "Decentralization-promoting validator incentives"
weight = 5
+++

Inverse Rewards promotes decentralization by rewarding smaller validators more.

## The Problem

Traditional PoS leads to stake concentration:
- Larger validators earn more
- Rewards compound
- Few validators dominate

## The Solution

```
reward_multiplier = base_reward * (1 + inverse_factor / stake_ratio)
```

## Comparison

| Validator | Stake | Traditional | Inverse |
|-----------|-------|-------------|---------|
| A | 10% | 10% rewards | ~8% |
| B | 1% | 1% rewards | ~3% |
| C | 0.1% | 0.1% rewards | ~0.5% |

## Benefits

- **Promotes Decentralization** - Smaller validators are viable
- **Reduces Concentration** - Diminishing returns
- **Better Security** - More validators = better BFT
- **Fair Competition** - New validators can compete

## Configuration

```toml
[consensus.rewards]
inverse_rewards_enabled = true
inverse_factor = 0.5
min_stake_for_bonus = 1000
```
