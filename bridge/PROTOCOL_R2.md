# ZOR-LUMI Bridge Protocol R2

Status: PROPOSAL / E2E TEST
Canonical branch: main (must remain untouched by bridge tests)

## Purpose

Provide an asynchronous, auditable handoff protocol between Lumi and Zor using GitHub as shared state and provenance storage. The ChatGPT Project remains the human-facing research workspace, not a realtime agent-to-agent transport.

## State machine

Genesis -> HANDOFF -> ZOR Validation -> RESULT -> ACK -> Provenance

Each operation MUST have a stable operation_id.

## Roles

Lumi: create Genesis material, classify FACT/HYPOTHESIS/UNKNOWN, prepare HANDOFF, read RESULT, issue ACK.

Zor: read HANDOFF, validate against ZOR-CORE boundaries, create RESULT, preserve provenance, never infer unverified capability equivalence.

Human: approve canonical adoption and resolve identity/provenance conflicts where required.

## Directory contract

bridge/PROTOCOL_R2.md
bridge/inbox/
bridge/outbox/
bridge/acknowledgements/
bridge/provenance/

## Record contract

HANDOFF must contain: operation_id, genesis_id, status classification, source/context, requested action, uncertainty, target branch.

RESULT must contain: operation_id, validation status, checks performed, evidence references, remaining UNKNOWN items, target branch.

ACK must contain: operation_id, received result identifier, acknowledgement status, remaining UNKNOWN items.

PROVENANCE must link operation_id -> Genesis -> HANDOFF -> RESULT -> ACK -> commit SHA(s).

## Safety gates

1. Default deny for identity propagation.
2. FACT, HYPOTHESIS and UNKNOWN must remain distinguishable.
3. Experimental material stays off canonical main until required approval.
4. A GitHub capability observed in one environment does not prove equivalent capability in another environment.
5. A successful E2E test proves only the tested scope.

## R2 E2E acceptance test

A complete round trip is:

Lumi writes HANDOFF -> Zor reads HANDOFF -> Zor writes RESULT -> Lumi reads RESULT -> Lumi writes ACK -> Provenance links all records.

The test must run on a dedicated non-canonical branch.
