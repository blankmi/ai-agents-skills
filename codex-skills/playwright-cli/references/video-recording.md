# Video Recording

Use video recording when the deliverable is a visual artifact rather than a debug trace.

## Basic Flow

```bash
playwright-cli video-start
playwright-cli open https://example.com
playwright-cli snapshot
playwright-cli click e1
playwright-cli video-stop demo.webm
```

## Guidance

- Use descriptive filenames for recordings that will be shared.
- Prefer tracing instead of video when you need DOM or network inspection.
- Stop recording promptly to avoid oversized files.
