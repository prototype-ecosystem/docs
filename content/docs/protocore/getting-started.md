+++
title = "Getting Started"
description = "Set up and run a Proto Core node"
weight = 1
+++

## Prerequisites

- **Rust** 1.70+ from [rustup.rs](https://rustup.rs/)
- **Git**
- **Build tools**: `gcc`, `make`, `cmake`

## Installation

### Install Rust

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source ~/.cargo/env
```

### Clone and Build

```bash
git clone https://github.com/prototype-network/protocore.git
cd protocore

# Debug build
cargo build --workspace

# Release build (recommended)
cargo build --workspace --release
```

## Running a Node

### Initialize

```bash
./target/release/protocore init --config protocore.toml
```

### Start

```bash
./target/release/protocore --config protocore.toml
```

### Join Network

Update `protocore.toml` with bootnodes:

```toml
[p2p]
bootnodes = [
    "/ip4/192.168.1.1/tcp/30303/p2p/12D3KooW...",
]
```

## Verify

```bash
curl -X POST -H "Content-Type: application/json" \
    --data '{"jsonrpc":"2.0","method":"proto_syncing","params":[],"id":1}' \
    http://localhost:8545
```
