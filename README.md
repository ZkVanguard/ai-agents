# ZkVanguard AI Agents

Multi-agent AI swarm for autonomous crypto portfolio risk management.

## Overview

This repository contains the AI agent system that powers ZkVanguard's autonomous risk management:

### Core Agents
- **LeadAgent** - Orchestrates agent communication and task delegation
- **RiskAgent** - Analyzes portfolio risk metrics (VaR, Sharpe, drawdown)
- **HedgingAgent** - Determines optimal hedging strategies
- **SettlementAgent** - Executes blockchain transactions
- **ReportingAgent** - Generates human-readable summaries

### Communication
- **AgentCommunicationHub** - Inter-agent messaging and coordination
- Crypto.com AI Agent SDK integration for natural language processing

## Architecture

`
User Query -> LeadAgent -> RiskAgent -> HedgingAgent -> SettlementAgent
                                                              |
                                                        ReportingAgent
`

## Development

### Prerequisites
- Node.js 18+
- TypeScript

### Install
`ash
npm install
`

### Run Tests
`ash
npm test
`

## Integration

Agents integrate with:
- Crypto.com AI Agent SDK
- Moonlander perpetuals API
- VVS Finance
- Pyth Network price feeds

## License

Apache License 2.0

## Related Repositories

- [ZkVanguard](https://github.com/ZkVanguard/ZkVanguard) - Main application
- [contracts-evm](https://github.com/ZkVanguard/contracts-evm) - Solidity contracts
- [contracts-sui](https://github.com/ZkVanguard/contracts-sui) - Move contracts
- [zkp-engine](https://github.com/ZkVanguard/zkp-engine) - ZK-STARK proof engine
