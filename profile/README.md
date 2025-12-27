# Islamic Open Finance

**Building the future of Shariah-compliant financial infrastructure**

Islamic Open Finance (IOF) is an open-source platform providing enterprise-grade APIs and tools for Islamic banking and finance operations.

## Our Mission

To democratize access to Islamic finance technology by providing open, standardized, and compliant financial infrastructure that enables:

- **Banks & Financial Institutions**: Modernize operations with AAOIFI-compliant APIs
- **Fintechs**: Build innovative Islamic finance products faster
- **Developers**: Access well-documented SDKs and tools
- **Regulators**: Ensure compliance with clear audit trails

## Core Platform

| Repository | Description | Status |
|------------|-------------|--------|
| [app](https://github.com/Islamic-Open-Finance/app) | Main platform - Rail API, services, infrastructure | Production Ready |

## SDKs & Tools

| Repository | Description | Language |
|------------|-------------|----------|
| [iof-sdk-typescript](https://github.com/Islamic-Open-Finance/iof-sdk-typescript) | TypeScript/JavaScript SDK | TypeScript |
| [iof-sdk-python](https://github.com/Islamic-Open-Finance/iof-sdk-python) | Python SDK with async support | Python |
| [iof-openapi](https://github.com/Islamic-Open-Finance/iof-openapi) | OpenAPI 3.1 specifications | YAML |
| [iof-mock](https://github.com/Islamic-Open-Finance/iof-mock) | Mock server for testing | Docker |
| [iof-devtools](https://github.com/Islamic-Open-Finance/iof-devtools) | Developer utilities | Node.js |
| [iof-helm-charts](https://github.com/Islamic-Open-Finance/iof-helm-charts) | Kubernetes Helm charts | Helm |

## Key Features

### 29 Financial Rails
Complete API coverage for Islamic finance operations:
- **Contracts**: Murabaha, Musharaka, Ijara, Sukuk
- **Compliance**: KYC, AML, Shariah screening
- **Treasury**: Position management, P&L
- **Clearing**: Settlement, reconciliation
- **Reporting**: Regulatory submissions

### Enterprise-Grade Infrastructure
- Multi-tenant architecture with workspace isolation
- Role-based access control (170+ permissions)
- Usage-based billing with SKU entitlements
- Real-time webhooks for event streaming
- Comprehensive audit logging

### Standards Compliant
- AAOIFI Shariah Standards
- OBP (Open Bank Project) compatible
- ISO 20022 message formats
- SOC2 security controls

## Quick Start

### TypeScript/JavaScript
```typescript
import { IOFClient } from '@islamic-open-finance/sdk';

const client = new IOFClient({
  apiKey: 'your-api-key',
  environment: 'sandbox'
});

// Create a Murabaha contract
const contract = await client.contracts.create({
  type: 'murabaha',
  parties: [...],
  terms: {...}
});
```

### Python
```python
from iof_sdk import IOFClient

client = IOFClient(
    api_key="your-api-key",
    environment="sandbox"
)

# Create a Murabaha contract
contract = await client.contracts.create(
    type="murabaha",
    parties=[...],
    terms={...}
)
```

## Documentation

- [API Reference](https://docs.islamic-open-finance.com/api)
- [Quick Start Guide](https://docs.islamic-open-finance.com/quickstart)
- [Authentication](https://docs.islamic-open-finance.com/auth)
- [Webhooks](https://docs.islamic-open-finance.com/webhooks)
- [Islamic Finance Primer](https://docs.islamic-open-finance.com/primer)

## Community

- [Discussions](https://github.com/orgs/Islamic-Open-Finance/discussions)
- [Issues](https://github.com/Islamic-Open-Finance/app/issues)
- [Contributing](https://github.com/Islamic-Open-Finance/app/blob/main/CONTRIBUTING.md)

## License

All repositories are licensed under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0) with explicit patent grant for enterprise use.

## Trademark

Islamic Open Finance™ and IOF™ are trademarks. See [TRADEMARK.md](https://github.com/Islamic-Open-Finance/app/blob/main/open-source/TRADEMARK.md) for usage guidelines.

---

<p align="center">
  <strong>Built for the global Islamic finance ecosystem</strong>
</p>
