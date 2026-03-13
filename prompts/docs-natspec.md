# Documentation & NatSpec Prompts

---

### 1. Generate NatSpec for Entire Contract

**When to use:** Adding documentation before audit or open-sourcing.

```
Generate complete NatSpec documentation for this Solidity contract.

For the contract:
- @title — what this contract is
- @notice — plain English description for users
- @dev — technical notes for developers

For each function:
- @notice — what it does (for users)
- @dev — implementation notes (for devs)
- @param — each parameter explained
- @return — each return value explained

For each event:
- @notice — when it's emitted and what it means

For each custom error:
- @notice — when it's thrown and why

Output the full contract with NatSpec added inline.

Contract:
[PASTE CONTRACT CODE HERE]
```

---

### 2. Write Technical README for Solidity Project

**When to use:** Open-sourcing a project or submitting to a hackathon.

```
Write a professional README.md for this Solidity project.

Project name: [PROJECT NAME]
What it does: [1-2 SENTENCES]

Include these sections:
1. Overview — what problem it solves, why it matters
2. Architecture — contracts and their roles (brief)
3. Deployed contracts — table with name, address, link
4. Installation — git clone, forge install, forge build
5. Testing — forge test, forge coverage
6. Deployment — forge script command
7. Security — any audits, known limitations
8. License

Tone: professional but direct. No fluff.

Contracts deployed at:
[LIST CONTRACT ADDRESSES ON BASE MAINNET]

Key features:
[LIST 3-5 KEY FEATURES]
```

---

### 3. Explain Contract in Plain English

**When to use:** Non-technical stakeholders need to understand what a contract does.

```
Explain this Solidity contract in plain English for a non-technical audience.

The reader is: [DESCRIBE AUDIENCE, e.g., "a VC investor", "a community member", "a lawyer"]

Explain:
1. What the contract does (no code terms)
2. Who can use it and how
3. What happens to their money/tokens
4. What risks exist
5. What the admin/owner can and cannot do

Avoid: technical jargon, function names, code snippets.
Use: analogies, plain language, concrete examples.

Contract:
[PASTE CONTRACT CODE HERE]
```

---

### 4. Generate Deployment Documentation

**When to use:** Documenting a deployment for team or audit trail.

```
Generate a deployment report for this contract deployment.

Contract: [CONTRACT NAME]
Network: [BASE MAINNET / BASE SEPOLIA / etc.]
Deployed address: [0x...]
Deployer: [0x...]
Transaction: [0x...]
Block: [BLOCK NUMBER]
Date: [DATE]

Constructor arguments:
[LIST EACH ARG WITH ITS VALUE AND WHAT IT MEANS]

Post-deployment steps completed:
[LIST STEPS, e.g., "Ownership transferred to multisig", "Initial state set"]

Create:
1. Deployment summary (1 paragraph)
2. Constructor args table with decoded values
3. Verification command (forge verify-contract)
4. Initial state verification commands (cast call for each key state variable)
5. Links (BaseScan contract, transaction)
```
