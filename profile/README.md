<p align="center"><img src="https://palisec.tech/brand/palisec-mark-512.png" alt="Palisec" width="96" height="96"></p>

<h1 align="center">Palisec</h1>

<p align="center"><b>Authorization and co-signer layer for AI agents on Robinhood Chain.</b></p>

An AI agent shouldn't hold a key that can do anything. With Palisec, the agent asks before it acts: every transaction is checked against the account's signed policy (contracts and functions, spend limits that count tokens, loss limits, asset safety) and co-signed only if the policy allows it. Refusals come back with a stable reason code.

**How it works.** The agent's account is a Safe with three owners and a threshold of two:

| Owner | Role |
|---|---|
| The agent's key | proposes and signs each transaction |
| Palisec's co-signer | signs only what the policy allows |
| Your recovery key | with the agent's key, can always change or leave the setup without Palisec |

Nothing moves without Palisec's co-signature, and Palisec can never move anything alone. Policies are published on chain through **ERC-8511**, so anyone can check which policy an account is under.

### Repositories

| Repo | What |
|---|---|
| [palisec](https://github.com/palisec/palisec) | The product: API, console, policy engines, contracts and SDKs |
| [policy-enforced-accounts](https://github.com/palisec/policy-enforced-accounts) | ERC-8511 reference library, registry contracts and test vectors |
| [policy-schema](https://github.com/palisec/policy-schema) | Policy schema, reason codes, the TypeScript reference evaluator and the Rust engine |
| [sdk-typescript](https://github.com/palisec/sdk-typescript) | `@palisec/sdk` |
| [sdk-python](https://github.com/palisec/sdk-python) | `palisec` for Python |
| [examples](https://github.com/palisec/examples) | Agents that ask Palisec first: Vercel AI SDK, OpenAI Agents SDK, LangGraph, MCP |

### Links

- **Docs:** [palisec.tech/docs](https://palisec.tech/docs) · [Changelog](https://palisec.tech/changelog)
- **ERC-8511:** [specification pull request](https://github.com/ethereum/ERCs/pull/2196) · [discussion](https://ethereum-magicians.org/t/erc-8511-policy-enforced-agent-accounts/30467)
- **Packages:** [`@palisec/sdk`](https://www.npmjs.com/package/@palisec/sdk) · [`palisec`](https://pypi.org/project/palisec/) · [`policy-enforced-accounts`](https://www.npmjs.com/package/policy-enforced-accounts)
- **X:** [@palisecagents](https://x.com/palisecagents) · **Security:** [security.txt](https://palisec.tech/.well-known/security.txt)
