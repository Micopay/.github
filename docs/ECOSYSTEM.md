# MicoPay Ecosystem

**Last updated:** October 30, 2026  
**Scope:** public repository map, architectural boundaries, and lifecycle conventions

## 1. Purpose

MicoPay is evolving from a single wallet into a collection of reusable financial components and vertical products. This document explains how those repositories relate to one another and prevents experimental work from being mistaken for production infrastructure.

The ecosystem separates three layers:

1. **Core infrastructure:** reusable identity, wallet, settlement, escrow, accounting, and integration components.
2. **Products:** applications for a particular market or workflow.
3. **Research and references:** experiments, educational implementations, and historical deliverables.

## 2. Architecture

```text
┌──────────────────────────── Products ────────────────────────────┐
│ MicoPay Café │ MicoPay Rentas │ Factoring │ future verticals   │
└───────────────────────────────┬──────────────────────────────────┘
                                │
┌────────────────────── Core infrastructure ───────────────────────┐
│ MicoPay Protocol │ MicoPay Issuer OS │ MicoPay Bridge           │
└───────────────┬───────────────────┬───────────────────┬──────────┘
                │                   │                   │
        ┌───────▼────────┐  ┌───────▼────────┐  ┌──────▼─────────┐
        │ Stellar       │  │ XRP Ledger     │  │ External rails │
        │ assets/escrow │  │ credit/settle  │  │ banks/providers│
        └────────────────┘  └────────────────┘  └────────────────┘
```

The diagram shows product dependencies, not a claim that every integration is already operational.

## 3. Core infrastructure

### MicoPay Protocol

Repository: [micopay-protocol](https://github.com/Micopay/micopay-protocol)

Responsibilities:

- mobile wallet and supporting backend;
- Stellar payments;
- cash-provider discovery and coordination;
- chat and transaction workflows;
- Soroban escrow integration;
- user-authorized signing and mobile key protection.

Does not own:

- agent-marketplace and x402 development;
- cross-network atomic-swap research;
- multi-issuer reserve accounting;
- product-specific lending underwriting.

### MicoPay Issuer OS

Repository: [micopay-issuer-os](https://github.com/Micopay/micopay-issuer-os)

Responsibilities proposed by the current design:

- multi-issuer financial ledger;
- asset, liability, and reserve reconciliation;
- controlled issuance, burn, and redemption workflows;
- provider-neutral connectors;
- asset and liquidity dashboards;
- ISO 20022-compatible canonical financial data;
- audit evidence and institutional permissions.

Current boundary: this is an architecture proposal, not a deployed issuer or regulated service.

### MicoPay Bridge

Repository: [micopaybridge](https://github.com/Micopay/micopaybridge)

Responsibilities:

- agent-to-agent markets;
- x402 payment services;
- atomic settlement experiments across XRPL and Stellar;
- machine-oriented escrow and cross-network workflows;
- related ZK and agent infrastructure.

Bridge remains separate from the retail cash network. Shared functionality must cross a versioned API boundary instead of being duplicated.

## 4. Products

### MicoPay Café

Repository: [micopay-cafe](https://github.com/Micopay/micopay-cafe)

A prototype for coffee buyers and cooperatives to calculate and settle producer payments, including crop-loan repayment and ISO 20022 records. It demonstrates how a vertical product can consume MicoPay payment infrastructure.

### MicoPay Rentas

Repository: [micopay-rentas](https://github.com/Micopay/micopay-rentas)

A testnet demonstration of rental escrow, cancellation policies, damage deposits, claims, and settlement. Listings are fictional and the repository must remain explicit about its testnet status.

### MicoPay Factoring

Repository: [factoring](https://github.com/Micopay/factoring)

Research into CFDI-backed factoring for Mexican businesses. Its domain logic includes invoice verification, legal assignment, underwriting, credit concentration, collections, defaults, and protection against double financing.

Factoring can reuse identity, accounting, reconciliation, and settlement components, but its credit-risk logic must remain outside the generic issuer and escrow cores.

## 5. Research, references, and historical repositories

### Coffee Payments

Repository: [coffee-payments](https://github.com/Micopay/coffee-payments)

An educational desktop implementation combining XRPL and ISO 20022. It is a useful reference, while MicoPay Café represents the newer product direction. The repositories should not silently duplicate features.

### Avales Líquidos

Repository: [AvalesLiquidos](https://github.com/Micopay/AvalesLiquidos)

An experimental XRPL testnet reference for liquid rental guarantees. Its README correctly separates published rails from operating a capital pool or custody service.

### BB101 Deliverables

Repository: [proyectobb101](https://github.com/Micopay/proyectobb101)

Program deliverables retained for historical traceability. New product development should move to the canonical product repositories.

### MicoPay Web

Repository: [micopay-landig](https://github.com/Micopay/micopay-landig)

The public website and lead-capture application. The repository name contains a historical typo; renaming it to `micopay-landing` is a separate cleanup decision because external integrations and deployment settings must be checked first.

## 6. Status vocabulary

Every public repository should declare one of these states near the top of its README:

| Status | Meaning |
|---|---|
| Production | Operated with real users or funds, with documented deployment and support boundaries |
| Active development | Maintained implementation whose production scope must still be stated explicitly |
| Prototype | Working demonstration that is not offered as a production service |
| Testnet demo | Demonstration restricted to test networks and test assets |
| Architecture and design | Planned system with documents but no complete implementation |
| Research | Investigation, market analysis, or feasibility work |
| Reference project | Educational or reusable example, not a supported product |
| Program archive | Historical deliverables retained for traceability |
| Archived | Read-only repository no longer under active development |

## 7. Repository conventions

### Naming

- Use lowercase kebab-case.
- Prefix product and infrastructure repositories with `micopay-` where practical.
- Avoid generic names when the repository belongs to a specific vertical.
- Preserve redirects and check deployments before renaming an existing repository.

### Required README information

- purpose and intended users;
- explicit maturity status;
- network and environment;
- custody model;
- setup and test instructions;
- known limitations;
- security reporting route;
- relationship to other MicoPay repositories;
- disclaimer where financial functionality is experimental.

### Topics

All repositories use `micopay` and `open-finance`, plus domain-specific topics such as `stellar`, `xrpl`, `payments`, `escrow`, `factoring`, `iso-20022`, `rwa`, or `x402`.

## 8. Architectural rules

1. Identify every asset using network, issuer, contract, and asset code rather than ticker alone.
2. Treat blockchain events, business state, and accounting entries as separate records that require reconciliation.
3. Make custody, redemption, and signing authority explicit for every product.
4. Keep product-specific risk logic out of generic settlement components.
5. Use versioned APIs and durable events between repositories.
6. Do not describe planned or testnet functionality as implemented production behavior.
7. Keep personal, fiscal, identity, and commercial documents out of public repositories.

## 9. Cleanup backlog

- evaluate renaming `micopaybridge` to `micopay-bridge`;
- evaluate renaming `micopay-landig` to `micopay-landing`;
- document whether `coffee-payments` is a predecessor or maintained reference for `micopay-cafe`;
- document the boundary between `AvalesLiquidos` and `micopay-rentas`;
- move new BB101-derived product work to canonical repositories;
- add consistent status notices and security policies to every active repository;
- archive repositories only after preserving links to their successors.

## 10. Governance

The organization profile is the public index. Each repository remains the source of truth for its own code and deployment status. Cross-project architectural decisions should be documented here and linked from the affected repositories.

