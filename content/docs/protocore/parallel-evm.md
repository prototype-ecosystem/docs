+++
title = "Parallel EVM"
description = "Concurrent transaction execution"
weight = 4
+++

Proto Core executes transactions in parallel when they don't conflict.

## How It Works

1. **Dependency Analysis** - Build conflict graph
2. **Scheduling** - Group independent transactions
3. **Parallel Execution** - Execute groups concurrently
4. **Deterministic Merge** - Combine results

## Performance

| Scenario | Sequential | Parallel (4 cores) |
|----------|------------|-------------------|
| Token transfers | 1,000 TPS | ~3,800 TPS |
| DEX trades | 1,000 TPS | ~2,200 TPS |
| Complex DeFi | 1,000 TPS | ~1,400 TPS |

## Determinism

Results are always deterministic:
- Same dependency analysis algorithm
- Fixed execution order within groups
- Deterministic state merge

All nodes arrive at the same state root.

## Configuration

```toml
[evm]
parallel_execution = true
max_parallel_threads = 4
speculation_depth = 2
```

## Compatibility

- Fully EVM-compatible
- Existing contracts work unchanged
- Same gas costs and semantics
- Transparent to developers
