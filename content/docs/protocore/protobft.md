+++
title = "ProtoBFT Consensus"
description = "Byzantine Fault Tolerant consensus mechanism"
weight = 3
+++

ProtoBFT is Prototype Network's consensus mechanism with fast finality and strong security.

## Key Properties

- **2-block finality** - Fast confirmation
- **Shuffled round-robin** - Fair proposer selection
- **VRF randomness** - Unpredictable and verifiable

## How It Works

1. **Proposer Selection** - VRF-based shuffled round-robin
2. **Block Proposal** - Selected validator creates block
3. **Voting** - Validators vote (prevote → precommit)
4. **Finalization** - Block finalized after 2 subsequent blocks

## Security Guarantees

| Property | Guarantee |
|----------|-----------|
| **Safety** | No conflicting finalized blocks |
| **Liveness** | Network continues progress |
| **Fault Tolerance** | Tolerates up to 1/3 Byzantine validators |

## VRF Randomness

Each block includes VRF proof for randomness beacon:

```rust
struct BlockHeader {
    // ... other fields
    vrf_proof: VrfProof,
    vrf_output: [u8; 32],
}
```

## Configuration

```toml
[consensus]
validator = true
validator_key = "/path/to/key"

[consensus.protobft]
block_time = 2000  # ms
finality_depth = 2
```
