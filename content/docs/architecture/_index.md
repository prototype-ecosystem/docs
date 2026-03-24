+++
title = "Architecture"
description = "Proto Core system architecture"
weight = 2
sort_by = "weight"
+++

Proto Core uses a modular architecture with 13 specialized Rust crates.

## Overview

```
┌─────────────────────────────────────────┐
│              RPC Layer                  │
└─────────────────┬───────────────────────┘
                  │
┌─────────────────┴───────────────────────┐
│           Application Layer             │
│  Mempool │ EVM │ Consensus │ State Sync │
└─────────────────┬───────────────────────┘
                  │
┌─────────────────┴───────────────────────┐
│             Core Layer                  │
│   Types │ Crypto │ Storage │ Config    │
└─────────────────┬───────────────────────┘
                  │
┌─────────────────┴───────────────────────┐
│           Network Layer (libp2p)        │
└─────────────────────────────────────────┘
```

## Crate Structure

| Crate | Purpose |
|-------|---------|
| `protocore` | Main node binary |
| `types` | Core types (Block, Transaction) |
| `crypto` | ECDSA, BLS, Schnorr, VRF |
| `config` | Configuration handling |
| `storage` | RocksDB + State DB |
| `consensus` | ProtoBFT consensus |
| `evm` | EVM + Parallel execution |
| `p2p` | libp2p networking |
| `mempool` | Transaction pool |
| `rpc` | JSON-RPC server |
| `light-client` | Light client |
| `state-sync` | State synchronization |
| `privacy` | Stealth addresses |
| `cli` | CLI tool |

## Addressing

Prototype uses **EVM-native addressing only** (0x-prefixed hex). No bech32 or Cosmos-style addresses. Fully compatible with MetaMask and standard Ethereum tooling.

## Design Principles

- **Modularity** - Single responsibility per crate
- **Performance** - Async I/O, parallel execution
- **Safety** - Rust memory safety, comprehensive errors
- **Determinism** - RLP encoding, BTreeMap ordering for identical state roots across nodes
- **Extensibility** - Plugin architecture
