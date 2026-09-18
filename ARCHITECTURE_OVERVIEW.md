# ZOR-CORE Architecture Overview

## Core Identity
V5-NATIVE-SYMBOLIC + CEV

## Integrated CEV
Input → Artifact Intake / Boundary → Metadata / Audit → Task / Checkpoint → Parallel Independent Execution → Per-Output Verification → Blind / Comparative Grading → Conditional Routing → EvidenceGraph → Synthesis → Provenance-Preserving Artifact → Replay / Export → Self-Diagnosis

## Core principles
- Routing decisions are observable and provenance-preserving.
- Execution resources and parallel admission are bounded.
- Artifact paths remain inside declared boundaries.
- Audit/control metadata is separated from data-plane payloads.
- Confidence is preserved.
- Replayable cache entries are content-digest addressed.
- Retry records attempt, seed when applicable, reason, and policy decision.
- Rejected, failed, and negative verification evidence is retained.
- Architecture revisions are versioned and non-destructive.

## External integration boundary
External evidence is audited before concept extraction and ZOR mapping. Concepts are independently implemented and validated before canonical adoption is considered. External capability equivalence is not claimed without independent validation.
