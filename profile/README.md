# Islamic Open Finance™

**Banking-grade Shariah-native infrastructure for the global Islamic finance ecosystem.**

Islamic Open Finance™ (IOF) is a platform composed from **10 native domain engines** over a single double-entry ledger, exposing **109 Shariah-native rails across 19 categories** (142+ API endpoints). It layers over Temenos, Finastra, Mambu, or Open Banking Protocol — no core replacement.

## Two Defensible Moats

Two of the ten engines are the platform's defensible moats — the economic reason a tier-1 balance sheet rents IOF instead of building in-house:

- **Settlement Engine** (`@iof/settlement-core`) — 24×7×365 DvP/FOP/RVP/DFP finality for Murabaha, Ijarah, Salam, Sukuk. AAOIFI SS-1/8/10/17/21/30 enforced at the state machine; CSDR Art. 7 LMFP/SEFP penalties priced pre-confirm; ribawi-pair netting honoured. Reclaims **60–140 bps** per corridor.
- **Evidence Engine** (`@iof/evidence-engine-core`) — signed, tamper-evident compliance pack on every trade. 47/54 controls across SOC 2, ISO 27001, AAOIFI, GDPR, PSD2, IFSB, ISO 20022. SHA-256 Merkle root + HMAC signature, one-call verification, JSON/CSV/PDF/ZIP export. Reclaims **30–55 bps** on audit + re-papering.

Combined: **100–195 bps** of Islamic-finance friction reclaimed per corridor.

## Mission

Make Shariah-native banking infrastructure boringly reliable and AAOIFI/IFSB/ISO 20022 compliant by default — for:

- **Banks & financial institutions** — modernise operations on AAOIFI-compliant rails without core replacement
- **Fintechs** — ship Shariah-compliant products in weeks instead of years
- **Developers** — typed SDKs, OpenAPI 3.1 specs, sandbox in one command
- **Regulators** — signed evidence packs and audit trails on every transaction

## SDKs & Tools

| Repository | Description | Language |
|------------|-------------|----------|
| [iof-sdk-typescript](https://github.com/Islamic-Open-Finance/iof-sdk-typescript) | TypeScript/JavaScript client for all rails + engines (`client.settlement.*`, `client.evidence.*`) | TypeScript |
| [iof-sdk-python](https://github.com/Islamic-Open-Finance/iof-sdk-python) | Python client for all rails + engines (`client.settlement.*`, `client.evidence.*`) | Python |
| [iof-openapi](https://github.com/Islamic-Open-Finance/iof-openapi) | OpenAPI 3.1 specification for the full 142+ endpoint surface | YAML |
| [iof-devtools](https://github.com/Islamic-Open-Finance/iof-devtools) | CLI + dev utilities (`iof settlement *`, `iof evidence export`) | Node.js |
| [iof-helm-charts](https://github.com/Islamic-Open-Finance/iof-helm-charts) | Kubernetes Helm charts for self-hosted deployment | Helm |

## Platform At a Glance

| Surface | Count |
|---|---|
| Native domain engines | **10** (2 are defensible moats) |
| Shariah-native rails | **109** |
| Rail categories | **19** |
| API endpoints | **142+** |
| Frameworks evidenced per trade | **7** (SOC 2, ISO 27001, AAOIFI, GDPR, PSD2, IFSB, ISO 20022) |
| Combined moat recovery | **100–195 bps** per corridor |

## Quick Start

### TypeScript

```typescript
import { IOFClient } from "@islamic-open-finance/sdk";

const client = new IOFClient({
  apiKey: process.env.IOF_API_KEY,
  environment: "sandbox",
});

// Create a Murabaha contract
const contract = await client.contracts.create({
  type: "murabaha",
  parties: [{ role: "seller", entityId: "e1" }, { role: "buyer", entityId: "e2" }],
  terms: { costPrice: 100000, profitMargin: 0.05, paymentSchedule: "monthly", tenure: 36 },
});

// Settle it on the moat rail (24×7×365 DvP, AAOIFI SS-enforced)
const settlement = await client.settlement.confirm({ contractId: contract.id, mode: "DVP" });

// Pull the signed compliance pack (47/54 controls, Merkle + HMAC)
const pack = await client.evidence.export({ tradeId: settlement.tradeId, format: "zip" });
```

### Python

```python
from iof_sdk import IOFClient

client = IOFClient(api_key="your-api-key", environment="sandbox")

contract = client.contracts.create(type="murabaha", parties=[...], terms={...})
settlement = client.settlement.confirm(contract_id=contract.id, mode="DVP")
pack = client.evidence.export(trade_id=settlement.trade_id, format="zip")
```

## Standards & Compliance

| Standard | Coverage |
|---|---|
| AAOIFI Shariah Standards | SS-1, SS-8, SS-10, SS-17, SS-21, SS-30 enforced at state machine |
| IFSB Prudential Standards | Capital adequacy, risk management, governance |
| ISO 20022 | All payment + settlement messages |
| SOC 2 Type II | Audit trails on every data access |
| ISO 27001 | ISMS controls, encryption, incident response |
| GDPR / PSD2 | Consent, SCA, data subject rights |
| Open Banking Protocol | OBP v5.1.0 compatible connector |

## Documentation

- [API Reference](https://docs.islamicopenfinance.com/api)
- [Quick Start Guide](https://docs.islamicopenfinance.com/quickstart)
- [Settlement Engine](https://docs.islamicopenfinance.com/engines/settlement)
- [Evidence Engine](https://docs.islamicopenfinance.com/engines/evidence)
- [Webhooks](https://docs.islamicopenfinance.com/webhooks)

## Community

- [Discussions](https://github.com/orgs/Islamic-Open-Finance/discussions)
- [Contributing](https://github.com/Islamic-Open-Finance/iof-sdk-typescript/blob/main/CONTRIBUTING.md)

## License

SDKs, cookbooks, and open-source connectors: [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0) with explicit patent grant for enterprise use. Core platform: proprietary.

## Trademark

Islamic Open Finance™ and IOF™ are trademarks. See trademark guidelines for usage.

---

<p align="center">
  <strong>Built for the global Islamic finance ecosystem.</strong>
</p>
