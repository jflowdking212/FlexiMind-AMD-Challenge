# Evaluation Plan

## Objective

Demonstrate that the AMD-backed execution path is not merely connected, but usable inside the FlexiMind orchestration loop.

## Initial Test Set

Start with 10–20 representative prompts in one chosen task family.

Each case should contain:
- case ID;
- input;
- expected properties;
- verifier;
- route;
- result status.

## Core Metrics

### Reliability
- execution success rate;
- verification pass rate;
- retry rate;
- failure reason.

### Performance
- end-to-end latency;
- model inference latency when available;
- time added by verification.

### Routing
- route chosen;
- fallback frequency;
- reroute frequency.

### Quality
Use task-specific objective checks first.

Examples:
- JSON parses;
- required fields are present;
- requested number of sections exists;
- output conforms to schema;
- reference facts supplied in the prompt are preserved.

For subjective output quality, publish the rubric and evaluation method.

## Benchmark File Format

Recommended CSV:

```csv
case_id,route,model,latency_ms,verified,retries,error
001,amd,<model>,0,true,0,
```

Do not invent benchmark numbers before tests are run.

## Comparison

If a comparison against an existing provider is included, use:
- identical inputs;
- same task contract;
- same verifier;
- repeated runs when variability matters.

Report the observed results rather than claiming one platform is universally faster or better.
