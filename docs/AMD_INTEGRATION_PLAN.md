# AMD Integration Plan

## Status

**Planned — not yet implemented.**

This document defines the implementation path. It must not be used as evidence that ROCm or AMD GPU execution is already working.

## Goal

Add one real AMD-backed inference path to FlexiMind while preserving the existing orchestration architecture.

The first successful milestone is intentionally simple:

> FlexiMind routes one supported task to an open-source model running on AMD infrastructure, receives the result, verifies it, and records execution metadata.

## Phase A — Environment

1. Confirm access to the AMD challenge compute/resource path.
2. Record the exact GPU/runtime provided.
3. Confirm the supported ROCm version.
4. Verify the GPU is visible to the runtime.
5. Save only non-sensitive environment evidence.

Evidence to capture:
- GPU model;
- ROCm/runtime version;
- framework version;
- successful minimal inference;
- timestamp / commit associated with the test.

## Phase B — Model Selection

Choose one model that:
- is permitted by the challenge;
- runs reliably on the available AMD environment;
- fits the available VRAM;
- supports the chosen demo workflow;
- can be started reproducibly.

Do not optimize for model size first. Optimize for:
1. reliable execution;
2. reproducibility;
3. measurable benefit;
4. integration simplicity.

Candidate model family can be finalized only after the actual AMD environment is known.

## Phase C — Inference Service

Expose the AMD model behind a small service or compatible inference API.

Required behavior:
- health endpoint;
- model identity endpoint or metadata;
- inference endpoint;
- timeout;
- structured error response;
- request ID;
- latency measurement.

## Phase D — FlexiMind Adapter

Add an adapter that maps the inference service to FlexiMind's normalized execution contract.

Pseudo-flow:

```ts
const result = await amdAdapter.execute({
  taskId,
  prompt,
  systemContext,
  timeoutMs
});

return {
  provider: "amd",
  model: result.model,
  output: result.text,
  latencyMs: result.latencyMs,
  rawUsage: result.usage
};
```

## Phase E — Routing

Start with a controlled routing rule.

Example:

```text
IF challenge_mode=true
AND task_type=analysis
AND amd_adapter=healthy
THEN route to AMD adapter
ELSE use existing fallback
```

Once reliable, replace the hard rule with capability/quality/latency-aware routing.

## Phase F — Verification

The demo task must have an explicit success condition.

Examples:
- valid JSON;
- required headings;
- answer contains all requested fields;
- task-specific checklist;
- comparison against a reference set.

## Phase G — Benchmark

For each test case record:
- route;
- model;
- latency;
- success/failure;
- verification result;
- retry count;
- qualitative notes.

Do not publish unsupported performance claims.

## Completion Criteria

AMD integration becomes **Implemented** only when all of the following exist in the repository:

- [ ] reproducible setup instructions;
- [ ] AMD adapter source;
- [ ] model/service configuration;
- [ ] successful end-to-end route;
- [ ] evidence of runtime;
- [ ] benchmark output;
- [ ] demo screenshot/video;
- [ ] no secrets committed.
