+++
title = "Architecture"
description = "Proto Core system architecture"
weight = 2
sort_by = "weight"
+++

Proto Core uses a modular architecture with 14 specialized Rust crates.

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

## Design Principles

- **Modularity** - Single responsibility per crate
- **Performance** - Async I/O, parallel execution
- **Safety** - Rust memory safety, comprehensive errors
- **Extensibility** - Plugin architecture
