# pricingagents

Agents for non-life and life insurance pricing.

**Status: early stage.** This release sets out the package structure and contains no functionality yet.

## How the packages fit together

Actuarial models live in plain libraries that don't depend on agents or LLMs. `pricingagents` holds everything agentic and builds on those libraries.

| Package | Purpose | Agentic? |
|---|---|---|
| [mammuthus](https://pypi.org/project/mammuthus/) | Non-life models, simulations, optimizers | No |
| [olivetree](https://pypi.org/project/olivetree/) | Life models, simulations, optimizers (reserved) | No |
| `pricingagents` | Agents, orchestration, MCP, review dashboard, audit trail | Yes |

```text
pricingagents
├── core       # LLM client, session log, review and override logic
├── nonlife    # agents, prompts, backends, MCP, dashboard
└── life       # reserved, not implemented
```

## Installation

```bash
pip install pricingagents
```

Optional extras are defined for the planned components:

| Extra | Installs | For |
|---|---|---|
| `agents` | `anthropic` | Agents with any backend |
| `nonlife` | `pricingagents[agents]` | Standard non-life install |
| `life` | `pricingagents[agents]` | Reserved |
| `mcp` | MCP SDK | MCP server without an LLM client |
| `dashboard` | `streamlit`, `plotly` | Review UI |

## License

MIT
