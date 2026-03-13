# Gas Optimization Prompts

---

### 1. Full Gas Audit

**When to use:** Optimizing a contract before mainnet deployment.

```
Audit this Solidity contract for gas optimization opportunities.

For each optimization, provide:
- What to change and where
- Why it saves gas (brief explanation)
- Estimated gas savings (if known)
- Risk level of the change (safe / medium / risky)

Prioritize by impact. Focus on:
- Storage reads/writes (most expensive)
- Loop optimizations
- Data type choices
- Function visibility
- Event vs storage tradeoffs
- Custom errors vs require strings

Contract:
[PASTE CONTRACT CODE HERE]
```

---

### 2. Optimize a Specific Function

**When to use:** One function is a gas bottleneck in your app.

```
Optimize this Solidity function for minimum gas cost without changing its behavior.

Current function:
[PASTE FUNCTION]

Constraints:
- Must maintain the same external interface (same function signature)
- Must emit the same events
- [ANY OTHER CONSTRAINTS]

Show the optimized version with inline comments explaining each change.
```

---

### 3. Storage Layout Optimization

**When to use:** You have a struct or many state variables and want to minimize slots.

```
Optimize the storage layout of this Solidity contract to minimize storage slots used.

Current state variables / struct:
[PASTE STATE VARIABLES OR STRUCT]

Rules:
- Each storage slot is 32 bytes
- Pack smaller types together if they fit in 32 bytes total
- Keep frequently accessed variables in the same slot

Show:
1. The current layout with slot assignments
2. The optimized layout
3. How many slots you saved
```

---

### 4. Compare Two Implementations for Gas

**When to use:** Choosing between two approaches.

```
Compare these two Solidity implementations for gas efficiency.

For each, estimate:
- Deployment cost
- Cost for the most common user operation
- Cost for edge cases

Then recommend which to use and why.

Implementation A:
[PASTE CODE A]

Implementation B:
[PASTE CODE B]

Context: The most common operation is [DESCRIBE COMMON USE CASE].
```

---

### 5. Loop and Iteration Optimization

**When to use:** Contract has loops that users call frequently.

```
Optimize these loops in my Solidity contract for gas efficiency.

[PASTE LOOPS / FUNCTIONS WITH LOOPS]

Apply these techniques where applicable:
- Cache array length outside loop
- Use unchecked { ++i } instead of i++
- Cache storage variables to memory before loop
- Use calldata instead of memory for read-only arrays
- Consider if the loop can be replaced with a mapping

Show the optimized version with explanations.
```
