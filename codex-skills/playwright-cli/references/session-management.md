# Session Management

Use named sessions with `-s=<name>` when you need separate cookies, storage, history, or tabs.

## Core Commands

```bash
playwright-cli -s=auth open https://app.example.com/login
playwright-cli -s=public open https://example.com
playwright-cli list
playwright-cli -s=auth close
playwright-cli close-all
playwright-cli kill-all
playwright-cli -s=auth delete-data
```

## Persistent Profiles

Use a persistent profile only when the task benefits from keeping auth or browser state across launches.

```bash
playwright-cli open https://example.com --persistent
playwright-cli open https://example.com --profile=/path/to/profile
```

## Practices

- Name sessions by purpose, such as `admin-login` or `checkout-debug`.
- Use separate sessions for different users or A/B variants.
- Close sessions when finished.
- Use `delete-data` to remove stale persistent state.
- Use `kill-all` only when normal cleanup does not work.
