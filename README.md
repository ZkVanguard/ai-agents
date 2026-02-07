# ZkVanguard AI Agents

> Multi-agent AI swarm system for autonomous crypto portfolio risk management

[![TypeScript](https://img.shields.io/badge/TypeScript-5.9-blue)](https://typescriptlang.org)
[![Crypto.com AI](https://img.shields.io/badge/Crypto.com-AI%20SDK-003CDA)](https://crypto.com)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue)](LICENSE)

## 6 Specialized Agents

| Agent | Module | Function |
|-------|--------|----------|
| **Lead** | `core/LeadAgent.ts` | Orchestrates workflow, natural language commands, approval gate |
| **Risk** | `specialized/RiskAgent.ts` | VaR, volatility, Sharpe ratio, liquidation risk analysis |
| **Hedging** | `specialized/HedgingAgent.ts` | Delphi-driven strategies via Moonlander perpetuals |
| **Settlement** | `specialized/SettlementAgent.ts` | x402 gasless execution with ZK authentication |
| **Reporting** | `specialized/ReportingAgent.ts` | Compliance reports, audit trails, analytics |
| **PriceMonitor** | `specialized/PriceMonitorAgent.ts` | Autonomous price alerts, triggers hedges on thresholds |

## Architecture

```
agents/
├── core/
│   ├── LeadAgent.ts            # Orchestrator + NLP via Crypto.com AI SDK
│   ├── BaseAgent.ts            # Abstract base class for all agents
│   ├── AgentRegistry.ts        # Agent discovery and lifecycle
│   └── SafeExecutionGuard.ts   # Execution safety boundaries
├── specialized/
│   ├── RiskAgent.ts            # Risk assessment engine
│   ├── HedgingAgent.ts         # Hedge strategy generation
│   ├── SettlementAgent.ts      # On-chain settlement execution
│   ├── ReportingAgent.ts       # Analytics and compliance
│   └── PriceMonitorAgent.ts    # Real-time price monitoring
├── communication/              # Inter-agent messaging
└── integrations/               # External service adapters
    ├── delphi/                 # Polymarket/Delphi prediction markets
    ├── mcp/                    # Model Context Protocol server
    ├── moonlander/             # Perpetual futures
    ├── vvs/                    # VVS Finance DEX
    └── x402/                   # Gasless transaction facilitator
```

## Agent Workflow

```
User (natural language) → Lead Agent → Task Decomposition
                                          │
                    ┌─────────────────────┼─────────────────────┐
                    ▼                     ▼                     ▼
               Risk Agent          Hedging Agent         PriceMonitor
               (analysis)         (strategy)            (alerts)
                    │                     │                     │
                    └─────────────────────┼─────────────────────┘
                                          ▼
                                   Lead Agent (approve)
                                          │
                              ┌───────────┴───────────┐
                              ▼                       ▼
                       Settlement Agent         Reporting Agent
                       (execute)                (audit trail)
```

## Setup

```bash
npm install

# Start agents
npx tsx agents/core/LeadAgent.ts

# Dev mode (watch)
npx tsx --watch agents/core/LeadAgent.ts
```

## Environment Variables

```env
CRYPTOCOM_DEVELOPER_API_KEY=   # Crypto.com AI SDK
CRYPTOCOM_AI_API_KEY=          # AI inference
NEXT_PUBLIC_MOONLANDER_API=    # Perpetuals
NEXT_PUBLIC_VVS_API=           # DEX swaps
NEXT_PUBLIC_X402_API=          # Gasless tx
NEXT_PUBLIC_DELPHI_API=        # Prediction markets
```

## Related Repos

- [ZkVanguard](https://github.com/ZkVanguard/ZkVanguard) — Main application
- [contracts-evm](https://github.com/ZkVanguard/contracts-evm) — Cronos EVM contracts
- [contracts-sui](https://github.com/ZkVanguard/contracts-sui) — SUI Move contracts
- [zkp-engine](https://github.com/ZkVanguard/zkp-engine) — ZK-STARK proof engine

## License

Apache 2.0
