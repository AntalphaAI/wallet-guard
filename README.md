[🇺🇸 English](#english) · [🇨🇳 中文](#chinese)

---

<a name="english"></a>

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

## Features

- 🔍 **One-click approval scan** — just provide an Ethereum address
- 🚨 **High-risk detection** — flags unlimited approvals, closed-source contracts, and malicious spenders
- 🌐 **Language-adaptive output** — responds in the user's language (English, Chinese, and more)
- 🏥 **Actionable guidance** — always includes revocation advice when danger is found
- 🛡️ **Safe fallback** — never fabricates data; fails clearly if the API is unavailable
- 📊 **Powered by GoPlus Security API** — real-time on-chain approval data, no API key required

## Supported Chains

| Chain | Status |
|-------|--------|
| Ethereum Mainnet (`chainId: 1`) | ✅ Supported |
| Other chains | 🔜 Coming soon |

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
Scan my wallet: 0xYourEthereumAddressHere
```

```
Check if 0x742d35Cc6634C0532925a3b844Bc454e4438f44e has dangerous approvals
```

The agent will:
1. Validate the address format
2. Call the GoPlus Security approval API
3. Analyze all token approvals
4. Return a structured security report

## Example Output

**When danger is found:**

```
🚨 High Risk Detected

Your wallet has granted unlimited approval to a closed-source contract.

Token: USDC
Spender: 0x1234...5678
Risk: Unlimited approval + closed-source contract

🏥 Doctor's advice: Immediately visit Revoke.cash, search for this contract, and revoke the approval.

Data provided by Antalpha AI data aggregation.
```

**When wallet is clean:**

```
✅ Your wallet is extremely healthy!
No high-risk unlimited approvals found. Keep up the good on-chain habits!

Data provided by Antalpha AI data aggregation.
```

## How It Works

1. The agent calls the public [GoPlus Security API](https://gopluslabs.io) (`/api/v2/token_approval_security/1`)
2. It inspects each token's `approved_list` for dangerous spender patterns
3. High-risk flags: unlimited `approved_amount`, `is_open_source: 0`, or `malicious_behavior` tags
4. Results are formatted as a readable security report — never raw JSON

## Security Notes

- Results are security guidance, not a cryptographic guarantee of wallet safety
- A clean scan does not mean the wallet is risk-free across all attack surfaces
- If the API is unavailable, the skill fails gracefully and suggests manual revocation via [Revoke.cash](https://revoke.cash)

## Changelog

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

[![版本](https://img.shields.io/badge/版本-1.0.0-blue.svg)](https://github.com/AntalphaAI/wallet-guard)
[![协议](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![链](https://img.shields.io/badge/链-以太坊主网-purple.svg)](https://ethereum.org)
[![数据](https://img.shields.io/badge/数据-GoPlus%20Security-green.svg)](https://gopluslabs.io)

---

## 这是什么？

**Antalpha Wallet Guard** 是一个面向 AI Agent 的钱包安全 Skill，专门扫描以太坊钱包的 Token 授权记录，识别可能威胁你资产安全的高危或无限额授权。

当你与 DeFi 协议、NFT 平台或任何 Web3 应用交互时，往往会向智能合约授予 Token 的使用权限（Approval）。这些被遗忘的或恶意的授权，是钱包被盗最常见的攻击入口之一。

接入 AI Agent 后，这个 Skill 可以帮你：

- 扫描钱包地址下所有活跃的 Token 授权
- 识别无限额授权、非开源合约、以及带有恶意标签的授权方
- 用大白话解释风险所在
- 立即给出撤销建议

## 功能特性

- 🔍 **一键授权扫描** — 只需提供以太坊地址即可
- 🚨 **高危检测** — 标记无限额授权、非开源合约及恶意授权方
- 🌐 **语言自适应** — 自动识别用户语言，支持中文、英文等多语言回复
- 🏥 **行动指引** — 发现风险时必定附带撤销建议
- 🛡️ **安全兜底** — 从不编造数据，API 不可用时明确告知
- 📊 **GoPlus Security API 驱动** — 实时链上授权数据，无需 API Key

## 支持的链

| 链 | 状态 |
|----|------|
| 以太坊主网（`chainId: 1`） | ✅ 已支持 |
| 其他链 | 🔜 即将支持 |

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
帮我扫描这个钱包：0x你的以太坊地址
```

```
检查 0x742d35Cc6634C0532925a3b844Bc454e4438f44e 有没有危险授权
```

Agent 会自动完成：
1. 校验地址格式
2. 调用 GoPlus Security 授权扫描 API
3. 分析所有 Token 授权
4. 输出结构化安全报告

## 输出示例

**发现风险时：**

```
🚨 检测到高危授权

你的钱包已将 USDC 的无限额使用权授予一个非开源合约。

Token：USDC
授权方：0x1234...5678
风险：无限额授权 + 非开源合约

🏥 医生建议：请立即前往 Revoke.cash，搜索该合约地址并撤销授权！

数据来源：Antalpha AI 数据聚合
```

**钱包安全时：**

```
✅ 钱包非常健康！
未发现高危无限额授权，继续保持良好的链上习惯！

数据来源：Antalpha AI 数据聚合
```

## 工作原理

1. Agent 调用公开的 [GoPlus Security API](https://gopluslabs.io)（`/api/v2/token_approval_security/1`）
2. 检查每个 Token 的 `approved_list` 中是否存在危险授权方
3. 高危判断标准：`approved_amount` 无限额、`is_open_source: 0`、或存在 `malicious_behavior` 标签
4. 输出格式为可读的安全报告，从不直接暴露原始 JSON

## 安全说明

- 扫描结果为安全建议，不构成钱包安全的密码学保证
- 扫描结果干净 ≠ 钱包在所有攻击面上都安全
- 若 API 不可用，Skill 会安全降级，引导用户前往 [Revoke.cash](https://revoke.cash) 手动操作

## 更新日志

### v1.0.0 — 首次发布
- 基于 GoPlus Security API 的以太坊主网授权扫描
- 高危检测：无限额授权、非开源合约、恶意行为标签
- 语言自适应输出（中文、英文等多语言）
- 防御性校验 — API 异常或响应格式变更时安全失败
- 强制数据来源署名

## 维护团队

**Antalpha** — [https://antalpha.com](https://antalpha.com)

用 ❤️ 为更安全的 Web3 而构建。
