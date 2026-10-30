# MicoPay

**Turn tokenized CETES and digital dollars into cash, without a bank.**

MicoPay is open financial infrastructure that connects digital assets on Stellar with physical cash in Mexico. A seller locks an asset in an on-chain escrow, meets a local cash provider, and receives pesos in hand. The provider receives the asset once the exchange is confirmed. Users keep their own keys, and MicoPay does not take custody of their funds.

MicoPay es infraestructura financiera abierta que conecta activos digitales en Stellar con efectivo en México. Quien vende bloquea su activo en un escrow en cadena, se reúne con un proveedor local de efectivo y recibe pesos en mano. El proveedor recibe el activo cuando se confirma el intercambio. Cada usuario conserva sus llaves y MicoPay no custodia sus fondos.

## Asset availability

| Asset | Cash exchange | Status |
|---|---|---|
| USDC (digital dollars) | Escrow-backed sale for cash | Stellar testnet; mainnet deployment pending |
| XLM | Escrow-backed sale for cash | Stellar testnet; mainnet deployment pending |
| Tokenized CETES | Escrow-backed sale for cash | In development; trading is gated |

## Ecosystem map

```text
Products
MicoPay cash network · MicoPay Café · MicoPay Rentas · Factoring
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
| [MicoPay Protocol](https://github.com/Micopay/micopay-protocol) | Mobile wallet, cash-provider network, chat, and escrow for selling digital assets for cash | Active development on testnet |
| [MicoPay Issuer OS](https://github.com/Micopay/micopay-issuer-os) | Multi-issuer accounting, reserves, reconciliation, and asset operations | Architecture and design |
| [MicoPay Bridge](https://github.com/Micopay/micopaybridge) | Agent payments, x402 services, atomic settlement, and cross-network experiments | Experimental |

## Products and verticals

| Project | Purpose | Status |
|---|---|---|
| [MicoPay cash network](https://github.com/Micopay/micopay-protocol) | Sale of digital assets for cash through local providers and escrow | Active development on testnet |
| [MicoPay Café](https://github.com/Micopay/micopay-cafe) | Payments to coffee producers with loan repayment and ISO 20022 records | Prototype |
| [MicoPay Rentas](https://github.com/Micopay/micopay-rentas) | Rental payments, cancellation rules, deposits, and dispute-aware escrow | Testnet demo |
| [MicoPay Factoring](https://github.com/Micopay/factoring) | CFDI-backed factoring research using XRPL credit primitives and MicoPay settlement | Research |

## Research and reference implementations

| Project | Purpose | Status |
|---|---|---|
| [Coffee Payments](https://github.com/Micopay/coffee-payments) | Educational XRPL and ISO 20022 desktop implementation | Reference project |
| [Avales Líquidos](https://github.com/Micopay/AvalesLiquidos) | Liquid rent-guarantee rails on XRPL | Experimental |
| [BB101 Deliverables](https://github.com/Micopay/proyectobb101) | Historical program deliverables | Program archive |
| [MicoPay Web](https://github.com/Micopay/micopay-landig) | Public website and lead-capture application | Website |

## Design principles

- **Non-custodial by design.** Users sign their own transactions, and funds move between their wallets and on-chain escrow rather than through a MicoPay account.
- **Custody must be explicit.** Every product must identify who holds funds, controls issuance, signs transactions, and promises redemption.
- **The real world remains part of the system.** Blockchain execution does not replace identity, accounting, legal rights, delivery evidence, or dispute resolution. The escrow tracks the digital side of an exchange; it cannot verify that cash changed hands.
- **Composable, separated components.** Products share APIs and financial primitives without mixing reserves, responsibilities, or private data.
- **Evidence before claims.** Repositories distinguish production behavior, testnet demonstrations, prototypes, and research.
- **Open standards.** Stellar ecosystem standards, XRPL primitives, and ISO 20022-compatible financial data reduce integration friction.

## Start here

- To understand the wallet and cash network, start with [MicoPay Protocol](https://github.com/Micopay/micopay-protocol).
- For institutional issuance, reserves, and reconciliation, read [MicoPay Issuer OS](https://github.com/Micopay/micopay-issuer-os).
- For agent payments and cross-network settlement, explore [MicoPay Bridge](https://github.com/Micopay/micopaybridge).
- For the complete repository map and boundaries, read [ECOSYSTEM.md](https://github.com/Micopay/.github/blob/main/docs/ECOSYSTEM.md).

## Contributing and security

Each repository documents its own setup, maturity, and contribution path. Check its README and open issues before starting work.

Do not disclose vulnerabilities in public issues. Report them privately to [eric@micopay.com.mx](mailto:eric@micopay.com.mx).

## Important notice

Experimental repositories, testnet demonstrations, and research documents are not financial services, investment products, or promises of availability or returns. Regulatory, legal, accounting, and custody responsibilities depend on the operator and deployment model of each product.
