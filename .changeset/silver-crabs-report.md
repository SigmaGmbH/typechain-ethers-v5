---
'@typechain/truffle-v5': major
---

Changed return type of functions from an array to a object. This represents better runtime types.

Before, solidity function like this:

```
function x() public pure returns (uint256)
```

Generated such method signature:

```typescript
x(txDetails?: Truffle.TransactionDetails): Promise<[BigNumber]>;
```

New output is:

```typescript
x(txDetails?: Truffle.TransactionDetails): Promise<{0: BigNumber}>;
```

The difference is that now you can use standard object destructuring while working with output types.