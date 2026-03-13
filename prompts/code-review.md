# Code Review Prompts

---

### 1. General Best Practices Review

**When to use:** Checking code quality before sharing or auditing.

```
Review this Solidity code for best practices and code quality.

Check for:
- Solidity version and pragma correctness
- Naming conventions (camelCase functions, PascalCase contracts, UPPER_CASE constants)
- Function visibility (public/external/internal/private — is each correct?)
- NatSpec documentation completeness
- Event emission on all state changes
- Custom errors vs require strings
- Correct use of view/pure
- Unnecessary storage reads
- Dead code or unreachable branches

Output as a checklist with PASS / FAIL / SUGGESTION for each item.

Contract:
[PASTE CONTRACT CODE HERE]
```

---

### 2. Refactor Legacy Solidity

**When to use:** Modernizing old contracts (0.6.x or 0.7.x) to 0.8.x+.

```
Refactor this legacy Solidity contract to modern 0.8.20 standards.

Changes to apply:
1. Update pragma to ^0.8.20
2. Remove SafeMath (built-in overflow checks in 0.8+)
3. Replace require("string") with custom errors
4. Update .transfer() and .send() to .call{value:}()
5. Add explicit function visibility (public/external/internal/private)
6. Use immutable for variables set once in constructor
7. Update ABI encoder to v2 if needed
8. Any other modernizations you see

Show the refactored contract with comments explaining each change.

Original contract (Solidity [VERSION]):
[PASTE OLD CONTRACT]
```

---

### 3. OpenZeppelin Compatibility Review

**When to use:** Using OZ contracts and want to verify correct usage.

```
Review my use of OpenZeppelin contracts in this Solidity code.

Check:
- Am I extending the right OZ base contracts for my use case?
- Am I calling super correctly in overridden functions?
- Are there any OZ functions I should be using but aren't?
- Is my initialization correct (for upgradeable contracts)?
- Am I using the latest recommended OZ patterns?
- Any deprecated OZ patterns I should update?

My contract:
[PASTE CONTRACT CODE]

OZ version I'm using: [VERSION, e.g., 5.0]
```

---

### 4. Find Magic Numbers and Constants

**When to use:** Cleaning up code before open-sourcing or auditing.

```
Find all magic numbers and hardcoded values in this Solidity contract and suggest named constants.

For each magic number:
- Where it appears
- What it represents
- Suggested constant name and value
- Suggested placement (contract-level constant or immutable)

Also flag:
- Hardcoded addresses that should be constructor parameters
- Hardcoded time durations (1 days, 7 days) that should be named
- Arbitrary limits that should be documented

Contract:
[PASTE CONTRACT CODE HERE]
```

---

### 5. Error Handling Review

**When to use:** Migrating from require strings to custom errors, or checking error coverage.

```
Review the error handling in this Solidity contract.

1. Convert all require("string") to custom errors
   - Name each error descriptively
   - Add parameters where useful (e.g., what value was expected vs actual)

2. Check for missing error handling:
   - Functions that should revert but don't
   - Missing zero-address checks
   - Missing bounds checks on inputs
   - Unchecked return values

3. Check return value handling:
   - All external .call() return values checked?
   - ERC-20 transfer/transferFrom return values handled?

Show the improved contract with all changes applied.

Contract:
[PASTE CONTRACT CODE HERE]
```
