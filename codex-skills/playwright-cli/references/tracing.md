# Tracing

Use tracing when you need a replayable debug artifact with DOM snapshots, screenshots, network activity, and console logs.

## Basic Flow

```bash
playwright-cli tracing-start
playwright-cli open https://example.com
playwright-cli click e1
playwright-cli fill e2 "test"
playwright-cli tracing-stop
```

## Best Uses

- Debug a failed click or missing element
- Inspect navigation timing and network activity
- Capture evidence for a flaky or timing-sensitive bug

## Guidance

- Start tracing before the problematic step.
- Stop tracing as soon as the reproducer is complete to keep artifacts smaller.
- Clean up old traces if the working directory accumulates large files.
