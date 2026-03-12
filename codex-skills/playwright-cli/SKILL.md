---
name: playwright-cli
description: Browser automation with the local `playwright-cli` binary for website navigation, UI testing, form filling, screenshots, PDFs, tab and session management, data extraction, and debugging rendered browser behavior. Use when Codex needs to control a real browser from the terminal, inspect a rendered page, interact with UI elements, capture artifacts, manage browser state, mock requests, or convert an observed flow into Playwright test code.
---

# Playwright CLI

Use `playwright-cli` for browser work that needs a real page, not just HTTP fetches. Prefer the globally installed `playwright-cli` binary in this environment. If that fails, retry with `npx playwright-cli`.

## Workflow

1. Start a browser session with `playwright-cli open <url>` or `playwright-cli -s=<name> open <url>`.
2. Read the latest snapshot after each action. Use the `eN` refs from that snapshot for subsequent commands.
3. Work in small steps: navigate, snapshot, interact, snapshot again after meaningful page changes.
4. Capture artifacts only when needed: screenshot, PDF, trace, video, or storage state.
5. Close the session when done with `playwright-cli close` or `playwright-cli close-all`.

## Core Commands

```bash
playwright-cli open https://example.com
playwright-cli goto https://playwright.dev
playwright-cli snapshot
playwright-cli click e3
playwright-cli fill e5 "user@example.com"
playwright-cli type "search text"
playwright-cli press Enter
playwright-cli select e8 "option-value"
playwright-cli check e12
playwright-cli close
```

## Navigation And Tabs

```bash
playwright-cli go-back
playwright-cli go-forward
playwright-cli reload
playwright-cli tab-new https://example.com/other
playwright-cli tab-list
playwright-cli tab-select 0
playwright-cli tab-close
```

## Artifacts And Inspection

```bash
playwright-cli snapshot
playwright-cli screenshot
playwright-cli screenshot e5
playwright-cli screenshot --filename=page.png
playwright-cli pdf --filename=page.pdf
playwright-cli eval "document.title"
playwright-cli eval "el => el.textContent" e5
```

## Browser Configuration

```bash
playwright-cli open --browser=chrome https://example.com
playwright-cli open --browser=firefox https://example.com
playwright-cli open --persistent https://example.com
playwright-cli open --profile=/path/to/profile https://example.com
playwright-cli resize 1440 900
```

## Guidance

- Prefer snapshots over guessing selectors. The `eN` refs are the fastest reliable way to continue a flow.
- Use named sessions with `-s=<name>` when you need isolation between logins, roles, or concurrent browser tasks.
- Use `--persistent` only when the user wants profile continuity across launches. Otherwise keep sessions ephemeral.
- Use `eval` for short DOM reads and `run-code` for anything requiring raw Playwright APIs, event handling, or conditional logic.
- Save files with explicit names when the artifact is part of the deliverable.
- If a session gets stuck, use `playwright-cli close-all` and then `playwright-cli kill-all`.

## References

- Read [references/session-management.md](references/session-management.md) for isolated sessions, cleanup, persistent profiles, and multi-browser workflows.
- Read [references/storage-state.md](references/storage-state.md) for cookies, localStorage, sessionStorage, and saved auth state.
- Read [references/request-mocking.md](references/request-mocking.md) for stubbing, blocking, or modifying network traffic.
- Read [references/running-code.md](references/running-code.md) when CLI subcommands are not enough and raw Playwright code is required.
- Read [references/tracing.md](references/tracing.md) for trace capture and debugging workflows.
- Read [references/video-recording.md](references/video-recording.md) for video capture.
- Read [references/test-generation.md](references/test-generation.md) when translating an interactive session into Playwright tests.

Keep the session short and explicit: open, inspect, interact, capture what matters, and clean up.
