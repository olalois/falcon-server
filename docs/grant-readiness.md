# Grant Readiness Brief

## Project

Falcon Server is the MIT-licensed backend for Access Layer, a Stellar-native creator keys marketplace. It provides off-chain API, creator metadata, indexing, notifications, and gated-access services that work alongside Stellar contracts. The intended beneficiaries are creators who want to offer token-based community access and the fans who participate in those communities.

## Public benefit

The project develops reusable, openly licensed infrastructure for creator-owned digital communities. Its scope includes the service layer needed to connect wallet-based ownership with ordinary web experiences, while keeping on-chain rules in the contracts. The source, API documentation, local setup, and contribution process are available in this repository for independent review and reuse.

## Existing evidence

- The [MIT license](../LICENSE) permits reuse and modification.
- The [domain-boundaries guide](./architecture/domain-boundaries.md) describes the server's responsibilities and module boundaries.
- The [Soroban contract service reference](./soroban-contract-service.md) documents transaction submission, retry, and resolution behavior.
- The [indexer documentation](./indexer/ARCHITECTURE.md) describes event processing and recovery workflows.
- The [local development guide](./local-development-setup.md) and [contributor seed guide](./contributor-seed.md) support reproducible evaluation without production data.
- The [CI workflow](../.github/workflows/ci.yml) runs lint and TypeScript builds on pushes and pull requests, with a separate PostgreSQL-backed invoice integration job.

## Proposed outcomes

These are candidate workstreams for a future grant proposal, not claims that the work is already funded or complete. Final scope and dates should be set with maintainers and the selected program.

### Reliable public indexing

- Publish a supported-event and data-freshness matrix for the indexer.
- Add or extend tests for duplicate delivery, retry, replay, and recovery paths.
- Document operational signals and a contributor-verifiable recovery procedure.

### Auditable creator access

- Document access decisions for unauthenticated users, verified owners, and non-owners.
- Add coverage for the documented authorization cases and failure behavior.
- Keep wallet ownership checks and sensitive actions traceable through the existing audit and event patterns.

### Sustainable maintenance

- Stabilize the broader Jest suite and make it a required CI check after its baseline failures are resolved; keep lint and TypeScript build required throughout.
- Maintain setup, security-reporting, release, and API-contract documentation as behavior changes.
- Break funded work into reviewable pull requests with public acceptance criteria and progress notes.

## Evaluation and reporting

Before submitting a proposal, establish a baseline from the current release and agree on target values with the funder. Report progress against published artifacts: documented event coverage, test and CI results, authorization scenarios covered, and completed operational guides. Do not infer user adoption or ecosystem impact from repository activity alone; collect beneficiary and usage measures only where maintainers can do so responsibly and consistently.

Budget, staffing, timeline, and numeric impact targets are intentionally left for a specific application. They depend on the grant program, maintainer capacity, and an agreed baseline; this brief does not imply a funding commitment or claim measured impact.