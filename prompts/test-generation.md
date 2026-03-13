# Test Generation Prompts

---

### 1. Comprehensive Foundry Test Suite

**When to use:** Starting tests for a new contract from scratch.

```
Generate a comprehensive Foundry test suite for this Solidity contract.

Include:
- setUp() with realistic initial state
- Happy path tests for every public function
- Revert tests for every require/revert/custom error
- Edge cases (zero values, max values, boundary conditions)
- Event emission tests using vm.expectEmit
- Access control tests (non-owner trying restricted functions)

Use:
- Foundry's Test, console from forge-std
- vm.prank() for different callers
- vm.deal() for ETH balances
- vm.warp() for time-dependent tests
- vm.expectRevert() for revert testing

Contract:
[PASTE CONTRACT CODE HERE]
```

---

### 2. Fuzz Tests

**When to use:** Testing with random inputs to find unexpected edge cases.

```
Generate Foundry fuzz tests for these functions in my contract.

For each function, create a fuzz test that:
- Uses random inputs (uint256, address, bytes, etc.)
- Uses vm.assume() to filter invalid inputs
- Checks invariants that should always hold
- Logs failures clearly with console.log

Functions to fuzz:
[PASTE FUNCTION SIGNATURES OR CODE]

Key invariants to check:
[DESCRIBE WHAT SHOULD ALWAYS BE TRUE, e.g., "total supply should never exceed MAX_SUPPLY"]

Contract context:
[PASTE RELEVANT CONTRACT CODE]
```

---

### 3. Fork Tests (Mainnet)

**When to use:** Testing integrations with real deployed protocols (Uniswap, Aave, etc.).

```
Generate Foundry fork tests for this contract that integrates with [PROTOCOL NAME].

Setup:
- Fork Base mainnet at a recent block
- Use real deployed contract addresses
- Use deal() to give test accounts real tokens

Test scenarios:
[DESCRIBE WHAT TO TEST]

Key addresses on Base:
- USDC: 0x833589fCD6eDb6E08f4c7C32D4f71b54bdA02913
- WETH: 0x4200000000000000000000000000000000000006
- Uniswap V3 Router: 0x2626664c2603336E57B271c5C0b26F421741e481

My contract:
[PASTE CONTRACT CODE]
```

---

### 4. Edge Case Tests

**When to use:** You have a specific scenario you're worried about.

```
Generate Foundry tests for these specific edge cases in my contract.

Edge cases to test:
1. [DESCRIBE EDGE CASE 1]
2. [DESCRIBE EDGE CASE 2]
3. [DESCRIBE EDGE CASE 3]

For each edge case:
- Set up the exact state that triggers it
- Test what happens
- Assert the expected outcome (either succeeds correctly or reverts with the right error)

Contract:
[PASTE CONTRACT CODE]
```

---

### 5. Invariant Tests

**When to use:** Verifying that fundamental properties always hold, regardless of operation order.

```
Generate Foundry invariant tests for this contract.

Invariants that must ALWAYS hold:
1. [DESCRIBE INVARIANT 1, e.g., "sum of all balances == totalSupply"]
2. [DESCRIBE INVARIANT 2]
3. [DESCRIBE INVARIANT 3]

Create:
- A handler contract with all state-changing operations as functions
- An invariant test contract that checks all invariants after each operation
- Appropriate ghost variables to track state across calls

Contract:
[PASTE CONTRACT CODE]
```
