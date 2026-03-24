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

## EVM-Native Addressing

Prototype uses **EVM-native addressing only** -- standard 0x-prefixed hex addresses (e.g., `0x71C7...`). There is no bech32 or Cosmos-style addressing. This means full compatibility with MetaMask, Hardhat, Foundry, and all standard Ethereum tooling out of the box.

## Production Hardening

Proto Core includes several hardening measures beyond the base PoC:

- **Deterministic state roots** -- RLP encoding with BTreeMap ordering ensures identical state across all nodes
- **Domain-aware BLS signing** -- Prevents cross-chain replay attacks by binding signatures to chain context
- **Prometheus metrics** -- Exposed on `:9090` for monitoring block production, peer count, mempool depth
- **Block sync protocol** -- Enables new nodes to sync historical blocks and join the network
- **6-second block time** -- Tuned for stability over raw speed
- **BLOCKHASH opcode** -- Supports the last 256 block hashes for smart contract compatibility
- **Crash recovery** -- WAL-based recovery so nodes resume cleanly after unexpected shutdown

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
