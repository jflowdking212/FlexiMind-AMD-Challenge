# Demo Plan

## Demo Objective

Show a reviewer one complete, understandable execution path in under three minutes.

## Recommended Demo Story

### 1. Problem — 15 seconds
Explain that users should not need to choose among AI models, tools, and agents manually.

### 2. Submit a Goal — 20 seconds
Enter one real task into FlexiMind.

Example class:
- structured business analysis;
- developer task;
- extraction / transformation task.

Use a task with a visible success condition.

### 3. Show Routing — 20 seconds
Display:
- detected task type;
- selected route;
- selected model/backend;
- AMD route status.

### 4. Execute on AMD — 30–45 seconds
Show the AMD-backed request executing.

Visible evidence should include at least one of:
- route badge;
- model/runtime metadata;
- safe runtime/health panel;
- trace ID tied to the execution.

### 5. Verification — 20 seconds
Show that FlexiMind checks the result rather than blindly returning it.

### 6. Final Result — 20 seconds
Display the normalized user-facing output.

### 7. Metrics — 20 seconds
Show:
- latency;
- verification result;
- retry count;
- model/route.

## Recording Rules

- never expose API keys;
- never expose production secrets;
- keep terminal output readable;
- zoom into important evidence;
- avoid long waits;
- use one workflow from start to finish;
- record a backup take.

## Demo Assets

Store public-safe screenshots and diagrams under `assets/`.
