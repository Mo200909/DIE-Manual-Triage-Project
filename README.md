# DIE Manual Triage Project

## Overview

This project demonstrates practical malware triage using Detect It Easy (DIE), a file-type identification tool used by security analysts to detect packers, compilers, and binary characteristics. The goal: learn to manually scan and classify files as packed or native, understanding how SOC analysts triage suspicious binaries.

## What I Did

1. Built a test file set: 6 Sysinternals EXEs in two states — Clean (native binaries) and Packed (UPX-compressed copies).
2. Scanned all 12 files using DIE's GUI, recording metadata: file type, compiler, OS target, architecture.
3. Identified the key differentiator: DIE flagged all Packed files with **(Heur) Packer: Generic [PE in resources]** in red, while Clean files showed no packer detection.
4. Documented findings in a structured table with 3 analysis questions.

## Key Findings

- **Clean vs. Packed**: Native binaries show no packer detection; UPX-compressed binaries trigger DIE's heuristic packer flag immediately.
- **Signature Limitation**: DIE relies on pre-built signatures — unknown or custom packers won't be detected.
- **SOC Workflow**: Packed files require escalation to sandbox, manual unpacking (UPX, memory dumps), or behavioral analysis.
- **Alternative Detection**: Entropy analysis (high entropy >7.0 = packed), behavioral sandboxing (observe runtime unpacking), and hex inspection work against unknown packers.

## Deliverables

- **DIE-Manual-Triage-Findings.md** — Complete findings table + 3-question analysis
- **Clean.pdf** — Screenshots of all 6 Clean file scans
- **Packed.pdf** — Screenshots of all 6 Packed file scans

## Skills Demonstrated

- Binary file analysis and classification
- Signature-based detection (DIE)
- Packer/obfuscation recognition
- SOC triage workflow understanding
- Alternative detection methods (entropy, sandboxing, manual inspection)
