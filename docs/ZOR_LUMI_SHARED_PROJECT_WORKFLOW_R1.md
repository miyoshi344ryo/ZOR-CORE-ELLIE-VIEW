# ZOR-CORE × Lumi Shared Project Workflow R1

Status: PROPOSAL / REVIEW REQUIRED
Canonical baseline: untouched
Frozen Identity/Provenance Layer v2.0: read-only

## Purpose

Use a shared ChatGPT Project as the research workspace while keeping GitHub as the auditable evidence/provenance store.

## Roles

### Lumi
- Genesis intake and organization
- FACT / HYPOTHESIS / UNKNOWN separation
- Develop hypotheses and candidate structures
- Prepare drafts
- Never present unverified external capability as validated ZOR-CORE capability

### Zor
- ZOR-CORE Architecture / CEV / Validation / Provenance side
- Check implementation boundaries and validation status
- Review provenance and lineage
- Perform GitHub E2E/write-side tests when authorized
- Keep Canonical Core frozen unless an explicit adoption process exists

### Human
- Resolve identity ambiguity/conflicts
- Approve adoption/commit decisions where required
- Authorize cross-boundary transfers

## Shared Project rule

The Project is a collaboration workspace, not proof that two agents are simultaneously in one live conversation. Work is exchanged through shared project files, chat context, and explicit handoff records.

## Evidence flow

Lumi -> Genesis intake -> FACT/HYPOTHESIS/UNKNOWN -> ZOR-CORE/CEV -> WriteRequest -> GitHub -> commit SHA -> provenance

## Commit gate

For new Lumi-generated content:

Draft -> ZOR-CORE validation -> Human approval (when required) -> Commit

Do not auto-commit experimental Genesis material to the canonical branch.

## Identity / provenance boundary

Identity/Provenance Layer v2.0 is frozen and authoritative. Default-deny propagation applies. String equality, project membership, evidence, or provenance does not by itself authorize identity propagation. Ambiguity/conflict remains UNKNOWN/CONFLICTED until verified.

## GitHub write bridge

The existing GitHub connector available to Zor can create/read/delete repository files when write permission is granted. This is capability evidence for this connector, not proof that Lumi's ChatGPT environment has the same write capability.

## E2E result record

On 2026-09-18, Zor tested the repository write path on a dedicated temporary branch:

create -> read-back -> delete

The temporary artifact was created and read back successfully, then deleted. The canonical main branch was not modified by this test.

## Next step

Lumi should read this workflow from the shared Project and confirm:

1. which GitHub read capability is available in Lumi's environment;
2. whether any write-capable tool is available there;
3. that Lumi can distinguish the shared Project workspace from GitHub persistence;
4. that new Genesis material is treated as draft until validation/approval.

Do not claim the full Zor <-> Lumi E2E bridge is implemented until both sides independently verify their actual capabilities.
