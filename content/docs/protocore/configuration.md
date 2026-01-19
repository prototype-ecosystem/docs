+++
title = "Configuration"
description = "Proto Core configuration reference"
weight = 2
+++

Proto Core uses `protocore.toml` for configuration.

## Example

```toml
[node]
name = "my-node"
data_dir = "./data"

[network]
chain_id = 1
network_id = 1

[p2p]
listen_addr = "/ip4/0.0.0.0/tcp/30303"
bootnodes = []
max_peers = 50

[rpc]
enabled = true
http_addr = "127.0.0.1"
http_port = 8545
ws_port = 8546

[consensus]
validator = false
validator_key = ""

[storage]
db_path = "./data/db"
state_cache_size = 1024

[mempool]
max_size = 10000

[logging]
level = "info"
```

## Options

| Section | Option | Default | Description |
|---------|--------|---------|-------------|
| `node` | `name` | `"protocore"` | Node identifier |
| `node` | `data_dir` | `"./data"` | Data directory |
| `p2p` | `listen_addr` | `"/ip4/0.0.0.0/tcp/30303"` | Listen address |
| `p2p` | `max_peers` | `50` | Max connections |
| `rpc` | `http_port` | `8545` | HTTP RPC port |
| `consensus` | `validator` | `false` | Validator mode |

## Environment Variables

Override with `PROTOCORE_` prefix:

```bash
export PROTOCORE_RPC_HTTP_PORT=9545
export PROTOCORE_CONSENSUS_VALIDATOR=true
```
