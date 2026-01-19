+++
title = "Account Abstraction"
description = "Native ERC-4337 smart contract wallets"
weight = 6
+++

Native support for smart contract wallets (ERC-4337).

## Features

- **Custom signatures** - Multisig, social recovery, biometrics
- **Gas sponsorship** - Pay in tokens or sponsored
- **Batched transactions** - Multiple operations atomically
- **Session keys** - Limited dApp permissions

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

### Social Recovery

Recover wallet via trusted contacts:

```solidity
function recover(address newOwner, bytes[] signatures) external {
    require(validSignatures(signatures) >= threshold);
    owner = newOwner;
}
```

### Gas Sponsorship

Paymaster pays transaction fees:

```solidity
function validatePaymasterUserOp(UserOperation op, ...) external {
    IERC20(token).transferFrom(op.sender, address(this), tokenAmount);
}
```

## Configuration

```toml
[evm.account_abstraction]
enabled = true
entrypoint_address = "0x5FF137D4b0FDCD49DcA30c7CF57E578a026d2789"
```
