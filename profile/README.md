# MicoPay

**Open financial infrastructure connecting self-custodial wallets, real-world payments, digital assets, and local settlement rails across Stellar and the XRP Ledger.**

MicoPay is an open ecosystem for moving value between blockchains, businesses, and the physical economy. We build reusable financial infrastructure and focused products for payments, escrow, asset operations, and access to liquidity.

MicoPay es un ecosistema abierto para conectar wallets autocustodiadas, pagos del mundo real, activos digitales y vías locales de liquidación. Construimos infraestructura financiera reutilizable y productos específicos para pagos, escrow, operación de activos y acceso a liquidez.

## Ecosystem map

```text
Products
MicoPay Café · MicoPay Rentas · Factoring
                         │
                         ▼
Core infrastructure
MicoPay Protocol · MicoPay Issuer OS · MicoPay Bridge
                         │
                         ▼
Networks and external rails
Stellar · XRP Ledger · regulated providers · local payment rails
```

## Core infrastructure

| Project | Purpose | Status |
|---|---|---|
| [MicoPay Protocol](https://github.com/Micopay/micopay-protocol) | Mobile wallet, Stellar payments, cash-provider coordination, chat, and escrow | Active development |
| [MicoPay Issuer OS](https://github.com/Micopay/micopay-issuer-os) | Multi-issuer accounting, reserves, reconciliation, and asset operations | Architecture and design |
| [MicoPay Bridge](https://github.com/Micopay/micopaybridge) | Agent payments, x402 services, atomic settlement, and cross-network experiments | Experimental infrastructure |

## Products and verticals

| Project | Purpose | Status |
|---|---|---|
| [MicoPay Café](https://github.com/Micopay/micopay-cafe) | Payments to coffee producers with loan repayment and ISO 20022 records | Prototype |
| [MicoPay Rentas](https://github.com/Micopay/micopay-rentas) | Rental payments, cancellation rules, deposits, and dispute-aware escrow | Testnet demo |
| [MicoPay Factoring](https://github.com/Micopay/factoring) | CFDI-backed factoring research using XRPL credit primitives and MicoPay settlement | Research and design |

## Research and reference implementations

| Project | Purpose | Status |
|---|---|---|
| [Coffee Payments](https://github.com/Micopay/coffee-payments) | Educational XRPL and ISO 20022 desktop implementation | Reference project |
| [Avales Líquidos](https://github.com/Micopay/AvalesLiquidos) | Liquid rent-guarantee rails on XRPL | Experimental testnet reference |
| [BB101 Deliverables](https://github.com/Micopay/proyectobb101) | Historical program deliverables | Program archive |
| [MicoPay Web](https://github.com/Micopay/micopay-landig) | Public website and lead-capture application | Website |

## Design principles

- **Self-custody when possible.** Users and institutional actors should retain control of their keys where the product permits it.
- **Custody must be explicit.** Every product must identify who holds funds, controls issuance, signs transactions, and promises redemption.
- **The real world remains part of the system.** Blockchain execution does not replace identity, accounting, legal rights, delivery evidence, or dispute resolution.
- **Composable, separated components.** Products share APIs and financial primitives without mixing reserves, responsibilities, or private data.
- **Evidence before claims.** Repositories distinguish production behavior, testnet demonstrations, prototypes, and research.
- **Open standards.** Stellar ecosystem standards, XRPL primitives, and ISO 20022-compatible financial data reduce integration friction.

## Start here

- To understand the consumer wallet and cash network, start with [MicoPay Protocol](https://github.com/Micopay/micopay-protocol).
- For institutional issuance, reserves, and reconciliation, read [MicoPay Issuer OS](https://github.com/Micopay/micopay-issuer-os).
- For agent payments and cross-network settlement, explore [MicoPay Bridge](https://github.com/Micopay/micopaybridge).
- For the complete repository map and boundaries, read [ECOSYSTEM.md](https://github.com/Micopay/.github/blob/main/docs/ECOSYSTEM.md).

## Contributing and security

Each repository documents its own setup, maturity, and contribution path. Check its README and open issues before starting work.

Do not disclose vulnerabilities in public issues. Use the repository's **Security** tab or GitHub private vulnerability reporting when available.

## Important notice

Experimental repositories, testnet demonstrations, and research documents are not financial services, investment products, or promises of availability or returns. Regulatory, legal, accounting, and custody responsibilities depend on the operator and deployment model of each product.

