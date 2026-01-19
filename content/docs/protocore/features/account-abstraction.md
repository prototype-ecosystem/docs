+++
title = "Account Abstraction"
description = "Native ERC-4337 smart contract wallets"
weight = 4
+++

Native support for smart contract wallets (ERC-4337).

## Features

- **Custom signatures** - Multisig, social recovery, biometrics
- **Gas sponsorship** - Pay fees in tokens or have others pay
- **Batched transactions** - Multiple operations atomically
- **Session keys** - Limited permissions for dApps

## UserOperation

```solidity
struct UserOperation {
    address sender;
    uint256 nonce;
    bytes initCode;
    bytes callData;
    uint256 callGasLimit;
    uint256 verificationGasLimit;
    uint256 preVerificationGas;
    uint256 maxFeePerGas;
    uint256 maxPriorityFeePerGas;
    bytes paymasterAndData;
    bytes signature;
}
```

## Use Cases

- **Social Recovery** - Recover wallet via trusted contacts
- **Gasless Transactions** - Paymaster sponsors fees
- **Batch Operations** - Multiple swaps in one tx

## Configuration

```toml
[evm.account_abstraction]
enabled = true
entrypoint_address = "0x5FF137D4b0FDCD49DcA30c7CF57E578a026d2789"
```
