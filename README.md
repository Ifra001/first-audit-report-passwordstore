# PasswordStore Smart Contract Audit

## Overview

This repository contains the security audit report for the PasswordStore smart contract, conducted by Ifra Muazzam. The audit was completed on May 16, 2025, with a focus on identifying vulnerabilities, assessing code quality, and providing mitigation strategies for detected issues.

## Table of Contents

* [Overview](#overview)
* [Audit Scope](#audit-scope)
* [Audit Summary](#audit-summary)

  * [High Severity Findings](#high-severity-findings)
  * [Informational Findings](#informational-findings)
* [Testing and Coverage](#testing-and-coverage)

## Audit Scope

* Repository: [PasswordStore Repository](https://github.com/Cyfrin/3-passwordstore-audit)
* Commit Hash: `7d55682ddc4301a7b13ae9413095feffd9924566`
* Files in Scope:

  * `./src/PasswordStore.sol`
* Solidity Version: `0.8.18`
* Target Chain: Ethereum

## Audit Summary

This audit reviewed the PasswordStore smart contract, which is designed to securely store and retrieve a password for a single user. The following findings were identified:

### High Severity Findings

1. **\[H-1] Storing the password on-chain makes it visible to anyone**

   * Impact: Anyone can access the stored password directly from the blockchain.
   * Recommendation: Encrypt the password off-chain before storing it.

2. **\[H-2] Missing Access Control for Password Setting**

   * Impact: Any user can set or change the password.
   * Recommendation: Restrict password-setting access to the contract owner.

### Informational Findings

* **\[I-1] Incorrect NatSpec for `getPassword` function**

  * Impact: Documentation misleads users.
  * Recommendation: Correct the NatSpec to match the function signature.

## Testing and Coverage

* Local Deployment: `make anvil` (starts a local blockchain)
* Deployment: `make deploy` (deploys the contract locally)
* Testing: `forge test` (runs the test suite)
* Coverage: `forge coverage` (generates test coverage report)

## Contact

* Auditor: Ifra Muazzam
* GitHub: [Ifra001](https://github.com/Ifra001)


