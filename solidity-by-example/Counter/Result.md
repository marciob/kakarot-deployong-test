## Counter Contract - Decrement Bug

### Overview

When decrementing from a count state of 0, the transaction unexpectedly completes instead of failing.

### Behavior

#### Current

With count at 0, calling the dec() function results in a successful transaction, keeping the count unchanged.

#### Expected

A reverted transaction with an error message:

```
transact to Counter.dec errored: VM error: revert.

revert
	The transaction has been reverted to the initial state.

```

### Reproduction

1. Deploy the `Counter.sol` and ensure Counter contract's count is 0.
2. Call `dec()` function.
3. Observe successful transaction.
