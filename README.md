# Antalpha Wallet Guard

> One-click scan for high-risk wallet approvals. Protect your assets before it's too late.

[![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)](https://github.com/AntalphaAI/wallet-guard)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Chain: Ethereum](https://img.shields.io/badge/chain-Ethereum%20Mainnet-purple.svg)](https://ethereum.org)
[![Data: GoPlus](https://img.shields.io/badge/data-GoPlus%20Security-green.svg)](https://gopluslabs.io)

---

## What Is This?

**Antalpha Wallet Guard** is a security skill for AI agents that scans Ethereum wallet token approvals and detects high-risk or unlimited allowances that could put your assets at risk.

When you interact with DeFi protocols, NFT marketplaces, or any Web3 dApp, you often grant token spending permissions (approvals) to smart contracts. Forgotten or malicious approvals are one of the most common vectors for wallet draining attacks.

This skill plugs into your AI agent and gives it the ability to:

- Scan a wallet address for all active token approvals
- Identify unlimited, closed-source, or maliciously flagged spenders
- Explain the risk in plain language
- Guide you to revoke dangerous approvals immediately

---

## Features

- 🔍 **One-click approval scan** — just provide an Ethereum address
- 🚨 **High-risk detection** — flags unlimited approvals, closed-source contracts, and malicious spenders
- 🌐 **Language-adaptive output** — responds in the user's language (English, Chinese, and more)
- 🏥 **Actionable guidance** — always includes revocation advice when danger is found
- 🛡️ **Safe fallback** — never fabricates data; fails clearly if the API is unavailable
- 📊 **Powered by GoPlus Security API** — real-time on-chain approval data, no API key required

---

## Supported Chains

| Chain | Status |
|-------|--------|
| Ethereum Mainnet (`chainId: 1`) | ✅ Supported |
| Other chains | 🔜 Coming soon |

---

## Installation

This skill is an **instruction-only** skill. No dependencies to install beyond `curl`.

```bash
# Install via clawhub
clawhub install antalpha-wallet-guard
```

Or clone manually:

```bash
git clone https://github.com/AntalphaAI/wallet-guard.git
```

---

## Usage

Once installed, simply ask your AI agent:

```
Scan my wallet: 0xYourEthereumAddressHere
```

```
Check if 0x742d35Cc6634C0532925a3b844Bc454e4438f44e has dangerous approvals
```

```
Do a wallet security check for 0x...
```

The agent will:
1. Validate the address format
2. Call the GoPlus Security approval API
3. Analyze all token approvals
4. Return a structured security report

---

## Example Output

**When danger is found:**

```
🚨 High Risk Detected

Your wallet has granted unlimited approval to a closed-source contract.

Token: USDC
Spender: 0x1234...5678
Risk: Unlimited approval + closed-source contract
This is equivalent to handing a stranger unrestricted access to your USDC.

🏥 Doctor's advice: Immediately visit Revoke.cash, search for this contract, and revoke the approval.

Data provided by Antalpha AI data aggregation.
```

**When wallet is clean:**

```
✅ Your wallet is extremely healthy!
No high-risk unlimited approvals found. Keep up the good on-chain habits!

Data provided by Antalpha AI data aggregation.
```

---

## How It Works

1. The agent calls the public [GoPlus Security API](https://gopluslabs.io) (`/api/v2/token_approval_security/1`)
2. It inspects each token's `approved_list` for dangerous spender patterns
3. High-risk flags: unlimited `approved_amount`, `is_open_source: 0`, or `malicious_behavior` tags
4. Results are formatted as a readable security report — never raw JSON

---

## Security Notes

- This skill uses the **public GoPlus Security API** — no API key required
- Results are security guidance, not a cryptographic guarantee of wallet safety
- A clean scan does not mean the wallet is risk-free across all attack surfaces
- If the API is unavailable, the skill will fail gracefully and suggest manual revocation via [Revoke.cash](https://revoke.cash)

---

## Changelog

### v1.0.0 — Initial Release
- Ethereum mainnet approval scan via GoPlus Security API
- High-risk detection: unlimited approvals, closed-source contracts, malicious behavior tags
- Language-adaptive output (English, Chinese, and more)
- Defensive validation — safe failure on API errors or schema changes
- Mandatory source attribution footer

---

## Maintainer

**Antalpha** — [https://antalpha.com](https://antalpha.com)

Built with ❤️ for safer Web3.
