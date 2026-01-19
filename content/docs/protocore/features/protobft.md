+++
title = "ProtoBFT Consensus"
description = "Byzantine Fault Tolerant consensus mechanism"
weight = 1
+++

ProtoBFT is Prototype Network's consensus mechanism.

## Key Properties

- **2-block finality** - Fast confirmation
- **Shuffled round-robin** - Fair proposer selection
- **VRF randomness** - Unpredictable and verifiable

## How It Works

1. **Proposer Selection** - VRF-based shuffled round-robin
2. **Block Proposal** - Selected validator creates block
3. **Voting** - Validators vote (prevote → precommit)
4. **Finalization** - Block finalized after 2 subsequent blocks

## Security

| Property | Guarantee |
|----------|-----------|
| Safety | No conflicting finalized blocks |
| Liveness | Network continues making progress |
| Fault Tolerance | Tolerates up to 1/3 Byzantine validators |

## Configuration

```toml
[consensus]
validator = true
validator_key = "/path/to/key"

[consensus.protobft]
block_time = 2000
finality_depth = 2
```
