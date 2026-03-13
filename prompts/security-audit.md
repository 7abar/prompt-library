# Security Audit Prompts

---

### 1. Full Contract Security Audit

**When to use:** Before deploying any contract to mainnet.

```
You are an expert Solidity security auditor. Audit the following contract for security vulnerabilities.

For each finding, provide:
- Severity: Critical / High / Medium / Low / Info
- Title
- Description of the vulnerability
- Location in code (function name or line)
- Recommended fix with code example

Also provide:
- Overall security score (A/B/C/D/F)
- Top 3 priorities before deployment
- Gas optimization opportunities

Contract:
[PASTE CONTRACT CODE HERE]
```

**Tips:** Use claude-opus for thorough results. Paste the entire file including imports.

---

### 2. Focused Reentrancy Check

**When to use:** Reviewing contracts that handle ETH or make external calls.

```
Review this Solidity contract specifically for reentrancy vulnerabilities.

Check every function that:
1. Makes external calls (call, delegatecall, transfer, send, or calls to external contracts)
2. Changes state before or after external calls
3. Uses the withdraw pattern

For each issue found, show the vulnerable code and the safe CEI (Checks-Effects-Interactions) version.

Contract:
[PASTE CONTRACT CODE HERE]
```

---

### 3. Access Control Review

**When to use:** Reviewing admin functions and permission systems.

```
Audit this contract's access control system.

For each function, tell me:
- Who can call it (owner only, anyone, specific role)
- Whether the restriction is appropriate for the function's power
- Any missing access controls
- Any functions that should be restricted but aren't

Also check:
- Is owner transfer two-step (nominate + accept)?
- Can the owner rug users? (upgradeable proxy, pausable, fee changes)
- Are there any privilege escalation paths?

Contract:
[PASTE CONTRACT CODE HERE]
```

---

### 4. Quick 5-Minute Scan

**When to use:** Fast initial review before deeper audit, or for simple contracts.

```
Quick security scan of this Solidity contract. Focus on:

1. Obvious critical vulnerabilities (reentrancy, unauthorized access, integer overflow)
2. Missing require/revert checks on critical operations
3. Unchecked return values from external calls
4. Any function that can drain funds

Be concise. List issues only — no need for detailed explanations unless critical.

Contract:
[PASTE CONTRACT CODE HERE]
```

---

### 5. Regression Check (v1 vs v2)

**When to use:** After refactoring or upgrading a contract.

```
Compare these two versions of a Solidity contract. I need to know:

1. Were any security issues from v1 fixed in v2?
2. Did v2 introduce any NEW security issues?
3. Were any important checks or validations accidentally removed?
4. Is the business logic equivalent (same behavior, just different implementation)?

v1 (original):
[PASTE V1 CONTRACT]

v2 (new version):
[PASTE V2 CONTRACT]
```

---

### 6. Single Function Audit

**When to use:** Deep review of one critical function (withdraw, swap, mint, etc.).

```
Deeply audit this specific function from a Solidity contract. Assume the rest of the contract is correct.

Function to audit:
[PASTE FUNCTION CODE]

Context (state variables and other relevant functions it calls):
[PASTE RELEVANT CONTEXT]

Check for:
- All possible ways this function could be exploited
- Edge cases that could cause unexpected behavior
- Whether the function behaves correctly with zero values, max values, and boundary conditions
- Front-running opportunities
- Any assumptions that could be violated
```
