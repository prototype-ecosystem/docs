+++
title = "Inverse Rewards"
description = "Decentralization-promoting validator incentives"
weight = 2
+++

Inverse Rewards promotes true decentralization by rewarding smaller validators proportionally more.

## The Problem

Traditional PoS leads to stake concentration - larger validators earn more, compound rewards, and dominate.

## The Solution

```
reward_multiplier = base_reward * (1 + inverse_factor / stake_ratio)
```

## Example

| Validator | Stake | Traditional | Inverse |
|-----------|-------|-------------|---------|
| A | 10% | 10% rewards | ~8% |
| B | 1% | 1% rewards | ~3% |
| C | 0.1% | 0.1% rewards | ~0.5% |

## Benefits

- Promotes decentralization
- Reduces stake concentration
- Better Byzantine fault tolerance
- Fair competition for new validators
