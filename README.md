[🇺🇸 English](#english) · [🇨🇳 中文](#chinese)

---

<a name="english"></a>

# Antalpha Wallet Guard

> One-click scan for high-risk wallet approvals. Protect your assets before it's too late.

[![Version](https://img.shields.io/badge/version-1.1.0-blue.svg)](https://github.com/AntalphaAI/wallet-guard)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Chain: Ethereum/BSC/Polygon/Base](https://img.shields.io/badge/chain-Multi--EVM-purple.svg)](https://ethereum.org)
[![Data: GoPlus](https://img.shields.io/badge/data-GoPlus%20Security-green.svg)](https://gopluslabs.io)

---

## What Is This?

**Antalpha Wallet Guard** is a security skill for AI agents that scans EVM wallet token approvals and detects high-risk or unlimited allowances across Ethereum, BSC, Polygon, and Base networks.

When you interact with DeFi protocols, NFT marketplaces, or any Web3 dApp, you often grant token spending permissions (approvals) to smart contracts. Forgotten or malicious approvals are one of the most common vectors for wallet draining attacks.

This skill plugs into your AI agent and gives it the ability to:

- Scan a wallet address for all active token approvals across multiple EVM chains
- Identify unlimited, suspicious, or maliciously flagged spenders
- Explain the risk in plain language
- Guide you to revoke dangerous approvals immediately

## Features

- 🔍 **One-click approval scan** — just provide a wallet address (chain auto-detected or specified)
- 🚨 **High-risk detection** — flags unlimited approvals, suspicious contracts, and malicious spenders
- 🌐 **Multi-chain support** — Ethereum, BSC, Polygon, Base (scanned automatically if no chain specified)
- 🌐 **Language-adaptive output** — responds in the user's language (English, Chinese, and more)
- 🏥 **Actionable guidance** — always includes revocation advice when danger is found
- 🛡️ **Safe fallback** — never fabricates data; fails clearly if the API is unavailable
- 📊 **Powered by GoPlus Security API** — real-time on-chain approval data, no API key required

## Supported Chains

| Chain | chainId | Status |
|-------|---------|--------|
| Ethereum Mainnet | `1` | ✅ Supported |
| BNB Smart Chain (BSC) | `56` | ✅ Supported |
| Polygon | `137` | ✅ Supported |
| Base | `8453` | ✅ Supported |
| Other EVM chains | — | 🔜 Coming soon |

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

## Usage

Once installed, simply ask your AI agent:

```
Scan my wallet: 0xYourWalletAddressHere
```

```
Check if 0x742d35Cc6634C0532925a3b844Bc454e4438f44e has dangerous approvals
```

```
帮我扫描这个 BSC 钱包：0x742d35Cc6634C0532925a3b844Bc454e4438f44e
```

```
Scan my Polygon wallet: 0x742d35Cc6634C0532925a3b844Bc454e4438f44e
```

The agent will:

1. Validate the address format
2. Detect which chain to scan (or scan all four chains if none specified)
3. Call the GoPlus Security approval API for each target chain
4. Analyze all token approvals
5. Return a structured security report per chain

## Example Output

**When danger is found:**

```
🚨 High Risk Detected

[Ethereum]
Token: USDC
Spender: 0x6c96...1dee
Risk: Unlimited approval

[BSC]
Token: BUSD
Spender: 0x1234...5678
Risk: Unlimited approval + suspicious contract

🏥 Doctor's advice: Please immediately use Revoke.cash, search for the contract address, and Revoke the access!

Data provided by Antalpha AI data aggregation.
```

**When wallet is clean:**

```
✅ Your wallet is extremely healthy!
No high-risk unlimited approvals found across Ethereum, BSC, Polygon, or Base. Keep up the good on-chain habits!

Data provided by Antalpha AI data aggregation.
```

## How It Works

1. The agent calls the public [GoPlus Security API](https://gopluslabs.io) (`/api/v2/token_approval_security/{chainId}`)
2. When no chain is specified, it scans Ethereum (1), BSC (56), Polygon (137), and Base (8453) in sequence
3. It inspects each token's `approved_list` for dangerous spender patterns using refined risk rules
4. High-risk flags: unlimited `approved_amount`, `doubt_list: 1`, `malicious_behavior` tags, or `is_open_source: 0` combined with suspicious signals
5. Results are formatted as a readable security report per chain — never raw JSON

## Security Notes

- Results are security guidance, not a cryptographic guarantee of wallet safety
- A clean scan does not mean the wallet is risk-free across all attack surfaces
- If the API is unavailable, the skill fails gracefully and suggests manual revocation via [Revoke.cash](https://revoke.cash)

## Changelog

### v1.1.0 — Multi-Chain Support
- Added support for BNB Smart Chain (chainId: 56), Polygon (chainId: 137), and Base (chainId: 8453)
- When no chain is specified, all four supported chains are scanned sequentially
- Refined high-risk detection: introduced `doubt_list` / `trust_list` signals to reduce false positives from closed-source contracts
- Clarified numeric unlimited approval threshold: > 2^96 (~79 septillion) is treated as unlimited
- Translation fix: "surfing habits" → "on-chain habits"
- Footer fix: "Antalpha Ai" → "Antalpha AI"

### v1.0.0 — Initial Release
- Ethereum mainnet approval scan via GoPlus Security API
- High-risk detection: unlimited approvals, closed-source contracts, malicious behavior tags
- Language-adaptive output (English, Chinese, and more)
- Defensive validation — safe failure on API errors or schema changes
- Mandatory source attribution footer

## Maintainer

**Antalpha** — [https://antalpha.com](https://antalpha.com)

Built with ❤️ for safer Web3.

---

<a name="chinese"></a>

# Antalpha Wallet Guard（钱包守卫）

> 一键扫描钱包高危授权，在资产被盗之前守住你的钱包。

[![版本](https://img.shields.io/badge/版本-1.1.0-blue.svg)](https://github.com/AntalphaAI/wallet-guard)
[![协议](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![链](https://img.shields.io/badge/链-多EVM链-purple.svg)](https://ethereum.org)
[![数据](https://img.shields.io/badge/数据-GoPlus%20Security-green.svg)](https://gopluslabs.io)

---

## 这是什么？

**Antalpha Wallet Guard** 是一个面向 AI Agent 的钱包安全 Skill，专门扫描以太坊、BSC、Polygon、Base 钱包的 Token 授权记录，识别可能威胁你资产安全的高危或无限额授权。

当你与 DeFi 协议、NFT 平台或任何 Web3 应用交互时，往往会向智能合约授予 Token 的使用权限（Approval）。这些被遗忘的或恶意的授权，是钱包被盗最常见的攻击入口之一。

接入 AI Agent 后，这个 Skill 可以帮你：

- 扫描钱包地址下所有活跃的 Token 授权（跨多条 EVM 链）
- 识别无限额授权、可疑合约、以及带有恶意标签的授权方
- 用大白话解释风险所在
- 立即给出撤销建议

## 功能特性

- 🔍 **一键授权扫描** — 只需提供钱包地址即可（链自动识别，或手动指定）
- 🚨 **高危检测** — 标记无限额授权、可疑合约及恶意授权方
- 🌐 **多链支持** — 以太坊、BSC、Polygon、Base（未指定链时自动扫描全部四条链）
- 🌐 **语言自适应** — 自动识别用户语言，支持中文、英文等多语言回复
- 🏥 **行动指引** — 发现风险时必定附带撤销建议
- 🛡️ **安全兜底** — 从不编造数据，API 不可用时明确告知
- 📊 **GoPlus Security API 驱动** — 实时链上授权数据，无需 API Key

## 支持的链

| 链 | chainId | 状态 |
|----|---------|------|
| 以太坊主网（Ethereum） | `1` | ✅ 已支持 |
| BNB Smart Chain（BSC） | `56` | ✅ 已支持 |
| Polygon | `137` | ✅ 已支持 |
| Base | `8453` | ✅ 已支持 |
| 其他 EVM 链 | — | 🔜 即将支持 |

## 安装方式

这是一个**纯指令型** Skill，除 `curl` 外无需安装任何依赖。

```bash
# 通过 clawhub 安装
clawhub install antalpha-wallet-guard
```

或手动克隆：

```bash
git clone https://github.com/AntalphaAI/wallet-guard.git
```

## 使用方式

安装后，直接向你的 AI Agent 发送：

```
帮我扫描这个钱包：0x你的钱包地址
```

```
检查 0x742d35Cc6634C0532925a3b844Bc454e4438f44e 有没有危险授权
```

```
帮我扫描 BSC 钱包：0x742d35Cc6634C0532925a3b844Bc454e4438f44e
```

```
扫描我的 Polygon 钱包：0x742d35Cc6634C0532925a3b844Bc454e4438f44e
```

Agent 会自动完成：

1. 校验地址格式
2. 识别要扫描的链（未指定则扫描全部四条链）
3. 调用 GoPlus Security 授权扫描 API
4. 分析所有 Token 授权
5. 输出结构化安全报告

## 输出示例

**发现风险时：**

```
🚨 检测到高危授权

【以太坊】
Token：USDC
授权方：0x6c96...1dee
风险：无限额授权

【BSC】
Token：BUSD
授权方：0x1234...5678
风险：无限额授权 + 可疑合约

🏥 医生建议：请立即前往 Revoke.cash，搜索该合约地址并撤销授权！

数据来源：Antalpha AI 数据聚合
```

**钱包安全时：**

```
✅ 钱包非常健康！
在以太坊、BSC、Polygon、Base 上均未发现高危无限额授权，继续保持良好的链上习惯！

数据来源：Antalpha AI 数据聚合
```

## 工作原理

1. Agent 调用公开的 [GoPlus Security API](https://gopluslabs.io)（`/api/v2/token_approval_security/{chainId}`）
2. 用户未指定链时，依次查询以太坊（1）、BSC（56）、Polygon（137）、Base（8453）四条链
3. 使用重构后的风险规则检查每个 Token 的 `approved_list` 中的危险授权方
4. 高危判断：无限额授权、`doubt_list: 1`、恶意标签、`is_open_source: 0` 配合可疑信号等
5. 输出格式为可读的安全报告，从不直接暴露原始 JSON

## 安全说明

- 扫描结果为安全建议，不构成钱包安全的密码学保证
- 扫描结果干净 ≠ 钱包在所有攻击面上都安全
- 若 API 不可用，Skill 会安全降级，引导用户前往 [Revoke.cash](https://revoke.cash) 手动操作

## 更新日志

### v1.1.0 — 多链支持
- 新增支持 BNB Smart Chain（chainId: 56）、Polygon（chainId: 137）和 Base（chainId: 8453）
- 用户未指定链时默认依次扫描全部四条支持链
- 重构高危检测规则：引入 `doubt_list` / `trust_list` 信号，减少闭源合约误报
- 明确数值型无限额授权阈值：> 2^96（约 7900 京）视为无限额
- 翻译修复："surfing habits" → "on-chain habits"
- Footer 修复："Antalpha Ai" → "Antalpha AI"

### v1.0.0 — 首次发布
- 基于 GoPlus Security API 的以太坊主网授权扫描
- 高危检测：无限额授权、非开源合约、恶意行为标签
- 语言自适应输出（中文、英文等多语言）
- 防御性校验 — API 异常或响应格式变更时安全失败
- 强制数据来源署名

## 维护团队

**Antalpha** — [https://antalpha.com](https://antalpha.com)

用 ❤️ 为更安全的 Web3 而构建。