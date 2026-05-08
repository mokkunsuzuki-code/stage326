# Stage326: Vulnerability Evidence Intake

Stage326 introduces the intake layer for REMEDA.

This stage binds:

- AI Claim
- Reproduction Result
- Evidence Files
- QSP Decision

## Core Problem

AI may report a vulnerability.

However, before trust scoring or public proof generation, REMEDA must verify:

> Is the AI claim referring to the same target as the reproduction result?

Without this intake layer, strong proof packages can still verify the wrong target.

## Intake Model

```text
AI Claim
   ↓
Reproduction Result
   ↓
Evidence Files
   ↓
QSP Decision
Core Rule
If AI Claim target != Reproduction Result target
→ reject or pending

Fail-closed remains enabled.

Public Files
docs/schema/vulnerability-evidence-intake.schema.json
docs/examples/demo-intake.json
Security Policy

This repository intentionally excludes:

private keys
secrets
databases
internal core logic
raw vulnerability evidence
local reproduction environments

Only sanitized public structures are published.

What Stage326 Proves

Stage326 proves that REMEDA can structurally bind AI vulnerability claims to reproduction evidence before making a verification decision.

License

MIT License

Copyright (c) 2025 Motohiro Suzuki
