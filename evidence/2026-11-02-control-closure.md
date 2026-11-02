# Evidence update - 2 November 2026

## What changed

Several current publications strengthen the distinction between **control coverage** and **control closure**.

### 1. OpenAI: detection and intervention are separate
OpenAI describes multiple automated monitoring layers for frontier-model misalignment and also states an important implementation boundary: observation can produce an alert without necessarily stopping execution when intervention support is unavailable.

**Architectural consequence:** evidence that a monitoring mechanism exists is not evidence that the intended intervention completed.

Source: https://openai.com/index/how-we-detect-frontier-model-misalignment/

### 2. METR / Redwood: a monitoring system can have gaps between control surfaces
The external red-team work on OpenAI's monitoring system found bypasses and coverage gaps in an earlier system state. OpenAI reports subsequent fixes; not every later fix has been independently re-tested by METR.

**Architectural consequence:** a green monitoring function does not imply complete trajectory coverage or independent assurance.

Source: https://metr.org/blog/2026-10-22-red-teaming-openai-agent-monitoring/

### 3. Anthropic: local control can fail across context and handoff boundaries
Anthropic reports attacks involving handoffs, context compaction, and agent-generated data. Experimental mitigations improved robustness without eliminating the broader class of problems.

**Architectural consequence:** per-action controls do not automatically prove continuity across an agent trajectory.

Source: https://alignment.anthropic.com/2026/red-teaming-auto-mode/

### 4. Distributed revocation: receipt is not enforcement
The paper "Revocation Is Not Complete at Receipt" experimentally separates delivery of revocation information from actual enforcement by distributed gateways.

**Architectural consequence:**

`revocation issued -> revocation delivered -> revocation stored`

is not equivalent to:

`all executors stopped authorizing -> harmful effect prevented -> new state proved`.

Source: https://arxiv.org/abs/2610.15991

### 5. SentinelOne: the market is already integrating several functions
SentinelOne publicly positions Agentic Detection and Response as an integrated layer spanning discovery, permissions, tracing, and isolation.

**Architectural consequence:** the relevant comparison is no longer "integrated architecture versus isolated tools". The stronger question is whether an integrated stack closes the entire required control relationship.

Source: https://www.sentinelone.com/press/sentinelone-launches-singularity-agentic-detection-and-response-to-stop-rogue-and-malicious-ai-agents-at-machine-speed/

## Public conclusion

The current claim is not that vendors lack controls. Many controls clearly exist and are increasingly integrated.

The claim is that:

> **Control presence and control closure are different properties.**

A useful public test therefore asks:

**Detected != Decided != Enforced != Effect stopped != State proved != Next action permitted.**

The F1-F9 map is intended to make those differences inspectable without requiring access to the internal TRINITY computation that generated the architecture.
