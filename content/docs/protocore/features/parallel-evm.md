+++
title = "Parallel EVM"
description = "Concurrent transaction execution"
weight = 3
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
| Token transfers | 1000 TPS | ~3800 TPS |
| DEX trades | 1000 TPS | ~2200 TPS |
| Complex DeFi | 1000 TPS | ~1400 TPS |

## Determinism

Results are always deterministic:
- Same dependency analysis algorithm
- Fixed execution order within groups
- Deterministic state merge

## Configuration

```toml
[evm]
parallel_execution = true
max_parallel_threads = 4
```
