+++
title = "Proto Core"
description = "Blockchain node implementation in Rust"
weight = 1
sort_by = "weight"
+++

Proto Core is the blockchain node implementation for Prototype Network, written in Rust for maximum performance and safety.

## Features

- **ProtoBFT Consensus** - Byzantine Fault Tolerant with 2-block finality
- **Parallel EVM** - Concurrent transaction execution
- **Inverse Rewards** - Fair validator reward distribution
- **Account Abstraction** - Native ERC-4337 support
- **State Rent** - Storage cost management
- **VRF Randomness** - Verifiable random functions
- **Binary Integrity** - 6-layer tamper prevention

## Crate Structure

```
crates/
├── protocore/        # Main binary
├── types/            # Core types
├── crypto/           # Cryptographic primitives
├── config/           # Configuration
├── storage/          # Database layer
├── consensus/        # ProtoBFT consensus
├── evm/              # EVM execution
├── p2p/              # Networking
├── mempool/          # Transaction pool
├── rpc/              # JSON-RPC
├── light-client/     # Light client
├── state-sync/       # State sync
├── privacy/          # Privacy features
└── cli/              # CLI tool
```

## Quick Start

```bash
# Clone
git clone https://github.com/prototype-network/protocore.git
cd protocore

# Build
cargo build --workspace --release

# Run
./target/release/protocore --config protocore.toml
```
