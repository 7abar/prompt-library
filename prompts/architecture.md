# Architecture Prompts

---

### 1. Review Contract Architecture Before Building

**When to use:** You have a design but haven't written code yet.

```
Review this proposed smart contract architecture before I build it.

What I'm building:
[DESCRIBE WHAT THE PROTOCOL DOES IN 2-3 SENTENCES]

Proposed contracts and their roles:
[LIST CONTRACTS AND WHAT EACH DOES]

Key design decisions I've made:
[LIST YOUR MAIN DECISIONS]

Questions I have:
[LIST SPECIFIC CONCERNS]

Please:
1. Identify design flaws or missing components
2. Suggest simpler alternatives if applicable
3. Flag any centralization or trust assumptions
4. Recommend proven patterns I should use
5. Estimate complexity (is this harder than I think?)
```

---

### 2. Design a System From Scratch

**When to use:** Starting a new protocol and want Claude to help design it.

```
Design a Solidity smart contract system for the following use case:

[DESCRIBE THE PROBLEM TO SOLVE]

Requirements:
- [REQUIREMENT 1]
- [REQUIREMENT 2]
- [REQUIREMENT 3]

Constraints:
- Target chain: Base (EVM compatible)
- Must minimize trust assumptions
- [ANY OTHER CONSTRAINTS]

Provide:
1. List of contracts needed and their responsibilities
2. Key data structures (structs, mappings)
3. Main function signatures with descriptions
4. How the contracts interact
5. Security considerations specific to this design
6. What NOT to build (out of scope)
```

---

### 3. Evaluate Upgrade Strategy

**When to use:** Deciding whether and how to make a contract upgradeable.

```
Help me decide on an upgrade strategy for this Solidity protocol.

Current situation:
[DESCRIBE WHAT THE PROTOCOL DOES AND ITS CURRENT STATE]

Options I'm considering:
- Transparent proxy (OpenZeppelin)
- UUPS proxy
- Beacon proxy (multiple instances)
- Immutable (no upgrades)
- Migration pattern (deploy new, migrate state)

My priorities (rank these): [SECURITY / FLEXIBILITY / SIMPLICITY / GAS COST]

Please:
1. Recommend the best approach for my situation
2. Explain the tradeoffs of each option
3. Describe the centralization risks of upgradeable contracts
4. If you recommend upgrades, show the minimal implementation pattern
```

---

### 4. Review for Centralization Risks

**When to use:** Checking how much power the admin/owner has.

```
Analyze this Solidity contract for centralization risks and trust assumptions.

For each privileged role or admin function, tell me:
- What power it grants
- What damage a malicious or compromised admin could do
- Whether this level of centralization is justified
- How to reduce the trust requirement (timelock, multisig, DAO, removing the function)

Also check:
- Can the protocol be paused by a single address?
- Can fees be changed without notice?
- Can user funds be moved by an admin?
- Are there any backdoors?

Contract:
[PASTE CONTRACT CODE HERE]
```

---

### 5. Multi-Contract System Design Review

**When to use:** You have multiple interacting contracts and want a holistic review.

```
Review the design of this multi-contract system.

Contracts in the system:
[LIST EACH CONTRACT WITH A 1-LINE DESCRIPTION]

How they interact:
[DESCRIBE THE MAIN FLOWS, e.g., "User calls ContractA, which calls ContractB, which calls ContractC"]

Current architecture diagram (text):
[PASTE ASCII DIAGRAM OR DESCRIPTION]

Review for:
1. Circular dependencies or circular calls that could cause issues
2. Attack surfaces at contract boundaries (who can call what)
3. State consistency — can the contracts get out of sync?
4. Gas efficiency of the cross-contract calls
5. Whether any contracts can be combined or split differently
6. Missing contracts or components

Contracts:
[PASTE ALL CONTRACT CODE OR INTERFACES]
```
